---
title: "Fullständig kodlista"
description: "Genomgång för att skicka data – fullständig kodlista"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 137ff1157d15b5a62ab7a66f30b1ba043747f75d
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2018
---
# <a name="push-data-to-a-dataset-complete-code-listing"></a>Fullständig kodlista för att skicka data till en datauppsättning
Den här artikeln ingår i en stegvis genomgång för att [skicka data till en datauppsättning](walkthrough-push-data.md).

När du har följt stegen 2 till 5 i **skicka data till en datauppsättning** bör den fullständiga källkoden se ut ungefär så här.

## <a name="push-data-to-dataset-code"></a>Kod för att skicka data till datauppsättning
      using System;
      using Microsoft.IdentityModel.Clients.ActiveDirectory;
      using System.Net;
      using System.IO;
      using Newtonsoft.Json;

      namespace walkthrough_push_data
      {
          class Program
          {
              private static string token = string.Empty;

              static void Main(string[] args)
              {

                  //Get an authentication access token
                  token = GetToken();

                  //Create a dataset in Power BI
                  CreateDataset();

                  //Get a dataset to add rows into a Power BI table
                  string datasetId = GetDataset();

                  //Add rows to a Power BI table
                  AddRows(datasetId, "Product");

              }

              #region Get an authentication access token
              private static string GetToken()
              {
                  // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                  // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                  //The client id that Azure AD created when you registered your client app.
                  string clientID = "{Client_ID}";

                  //RedirectUri you used when you register your app.
                  //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                  // You can use this redirect uri for your client app
                  string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                  //Resource Uri for Power BI API
                  string resourceUri = "https://analysis.windows.net/powerbi/api";

                  //OAuth2 authority Uri
                  string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                  //Get access token:
                  // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                  // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                  // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                  //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                  // AcquireToken will acquire an Azure access token
                  // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                  AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                  string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                  Console.WriteLine(token);
                  Console.ReadLine();

                  return token;
              }

              #endregion

              #region Create a dataset in Power BI
              private static void CreateDataset()
              {
                  //TODO: Add using System.Net and using System.IO

                  string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                  //POST web request to create a dataset.
                  //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                  HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                  request.KeepAlive = true;
                  request.Method = "POST";
                  request.ContentLength = 0;
                  request.ContentType = "application/json";

                  //Add token to the request header
                  request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                  //Create dataset JSON for POST request
                  string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                      "[{\"name\": \"Product\", \"columns\": " +
                      "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                      "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                      "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                      "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                      "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                      "]}]}";

                  //POST web request
                  byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
                  request.ContentLength = byteArray.Length;

                  //Write JSON byte[] into a Stream
                  using (Stream writer = request.GetRequestStream())
                  {
                      writer.Write(byteArray, 0, byteArray.Length);

                      var response = (HttpWebResponse)request.GetResponse();

                      Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                      Console.ReadLine();
                  }
              }
              #endregion

              #region Get a dataset to add rows into a Power BI table
              private static string GetDataset()
              {
                  string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                  //POST web request to create a dataset.
                  //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                  HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                  request.KeepAlive = true;
                  request.Method = "GET";
                  request.ContentLength = 0;
                  request.ContentType = "application/json";

                  //Add token to the request header
                  request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                  string datasetId = string.Empty;
                  //Get HttpWebResponse from GET request
                  using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
                  {
                      //Get StreamReader that holds the response stream
                      using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                      {
                          string responseContent = reader.ReadToEnd();

                          //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                          //and add using Newtonsoft.Json
                          var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                          //Get the first id
                          datasetId = results["value"][0]["id"];

                          Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                          Console.ReadLine();

                          return datasetId;
                      }
                  }
              }
              #endregion

              #region Add rows to a Power BI table
              private static void AddRows(string datasetId, string tableName)
              {
                  string powerBIApiAddRowsUrl = String.Format("https://api.powerbi.com/v1.0/myorg/datasets/{0}/tables/{1}/rows", datasetId, tableName);

                  //POST web request to add rows.
                  //To add rows to a dataset in a group, use the Groups uri: https://api.powerbi.com/v1.0/myorg/groups/{group_id}/datasets/{dataset_id}/tables/{table_name}/rows
                  //Change request method to "POST"
                  HttpWebRequest request = System.Net.WebRequest.Create(powerBIApiAddRowsUrl) as System.Net.HttpWebRequest;
                  request.KeepAlive = true;
                  request.Method = "POST";
                  request.ContentLength = 0;
                  request.ContentType = "application/json";

                  //Add token to the request header
                  request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                  //JSON content for product row
                  string rowsJson = "{\"rows\":" +
                      "[{\"ProductID\":1,\"Name\":\"Adjustable Race\",\"Category\":\"Components\",\"IsCompete\":true,\"ManufacturedOn\":\"07/30/2014\"}," +
                      "{\"ProductID\":2,\"Name\":\"LL Crankarm\",\"Category\":\"Components\",\"IsCompete\":true,\"ManufacturedOn\":\"07/30/2014\"}," +
                      "{\"ProductID\":3,\"Name\":\"HL Mountain Frame - Silver\",\"Category\":\"Bikes\",\"IsCompete\":true,\"ManufacturedOn\":\"07/30/2014\"}]}";

                  //POST web request
                  byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(rowsJson);
                  request.ContentLength = byteArray.Length;

                  //Write JSON byte[] into a Stream
                  using (Stream writer = request.GetRequestStream())
                  {
                      writer.Write(byteArray, 0, byteArray.Length);

                      var response = (HttpWebResponse)request.GetResponse();

                      Console.WriteLine("Rows Added");

                      Console.ReadLine();
                  }
              }

              #endregion
          }
      }


## <a name="next-steps"></a>Nästa steg
[Skicka data till en Power BI-datauppsättning](walkthrough-push-data.md)  
[Genomgång – Skicka data till en Power BI-datauppsättning](walkthrough-push-data.md)  
[Registrera en app med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[Hämta en åtkomsttoken för autentisering](walkthrough-push-data-get-token.md)  
[Skapa en datauppsättning i Power BI](walkthrough-push-data-create-dataset.md)  
[Hämta en datauppsättning för att lägga till rader i en Power BI-tabell](walkthrough-push-data-get-datasets.md)  
[Lägg till rader i en Power BI-tabell](walkthrough-push-data-add-rows.md)  
[Power BI REST API-referens](https://msdn.microsoft.com/library/mt147898.aspx)  
[Översikt över Power BI REST API](overview-of-power-bi-rest-api.md)  


Har du fler frågor? [Prova Power BI Community](http://community.powerbi.com/)
