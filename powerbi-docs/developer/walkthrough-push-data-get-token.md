---
title: "Hämta en åtkomsttoken för autentisering"
description: "Genomgång för att skicka data – hämta en åtkomsttoken för autentisering"
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
ms.openlocfilehash: 068baa78315bfc7e4f7078ed47596a480dbe3765
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2017
---
# <a name="step-2-get-an-authentication-access-token"></a>Steg 2: hämta en åtkomsttoken för autentisering
Den här artikeln ingår i en stegvis genomgång för att [skicka data till en datauppsättning](walkthrough-push-data.md).

I **steg 1** av Skicka data till en datauppsättning, [Registrera appen med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md), registrerade du en klientapp i Azure AD. I det här steget, hämtar du en åtkomsttoken för autentisering. Power BI-appar är integrerade med **Azure AD** för att tillhandahålla säker inloggning och auktorisering för din app. Du använder en token för att autentisera till **Azure AD** och få åtkomst till Power BI-resurser.

Så här hämtar du en åtkomsttoken för autentisering.

## <a name="get-an-authentication-access-token"></a>Hämta en åtkomsttoken för autentisering
> **Obs**: Innan du börjar kontrollerar du att du har följt föregående steg i genomgången [skicka data till en datauppsättning](walkthrough-push-data.md).
> 
> 

1. I Visual Studio 2015, skapar du ett **Konsolprogram**-projekt.
2. Installera [Azure AD-autentiseringsbiblioteket för .NET NuGet-paket](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/). Om du vill hämta en säkerhetstoken för autentisering i en .NET-app, använder du det här paketet. Så här installerar du paketet:
   
     a. I Visual Studio 2015 väljer du **Verktyg** > **NuGet-pakethanteraren** > **Pakethanterarkonsolen**.
   
     b. I **Pakethanterarkonsolen**, anger du Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory-Version 2.21.301221612.
3. Lägg till koden nedan i klassen Program {...}.
4. Ersätt ”{ClientID}”, med den **klient-ID** du fick när du registrerade appen. Se [Registrera appen med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).
5. När du har installerat Microsoft.IdentityModel.Clients.ActiveDirectory-paketet, lägger du till **using Microsoft.IdentityModel.Clients.ActiveDirectory;** till Program.cs.
6. Kör konsolappen och logga in på ditt Power BI-konto. Du bör se en tokensträng i konsolfönstret.

**Exempelkod för att hämta säkerhetstoken för autentisering**

Lägg till den här koden i Program {...}.

* En tokenvariabel för att anropa åtgärder:
  
  ```
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* In static void Main(string[] args):
  
  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Lägg till en GetToken()-metod:

```
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
```

När du får en autentiseringstoken, kan du anropa valfri Power BI-åtgärd. Nästa steg visar hur du anropar åtgärden [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx) för att skapa en datauppsättning för att skicka data till en instrumentpanel.

Nästa steg visar hur du [skapar en datauppsättning i Power BI](walkthrough-push-data-create-dataset.md).

Nedan visas den [fullständiga kodlistan](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Fullständig kodlista
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

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

        }
    }


[Nästa steg >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Nästa steg
[Skapa en datauppsättning i Power BI](walkthrough-push-data-create-dataset.md)  
[Registrera en app med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[Azure AD-autentiseringsbiblioteket för .NET NuGet-paket](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Skicka data till en Power BI-datauppsättning](walkthrough-push-data.md)  
[Översikt över Power BI REST API](overview-of-power-bi-rest-api.md)  
[Power BI REST API-referens](https://msdn.microsoft.com/library/mt147898.aspx)  
Har du fler frågor? [Prova Power BI Community](http://community.powerbi.com/)
