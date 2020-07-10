---
title: Crear una aplicación de portal de intranet de Teams desde un sitio o una página de SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Elija un sitio o una página de SharePoint Online ya existente y cree una pestaña estática independiente que se pueda usar como portal de intranet de su organización.
localization_priority: Priority
ms.openlocfilehash: 09ff3fd57eee23c5eec9dfac118b68938c1c9f36
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083170"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Crear una aplicación de portal de intranet de Teams desde un sitio o una página de SharePoint Online

Siga los pasos de este artículo para crear una aplicación independiente y estática en Teams que se vincule al sitio de intranet de su organización.

Se creará una *Aplicación personal de Teams* del sitio de intranet de SharePoint y se mostrará como una pestaña dentro de Teams. Esta pestaña puede contener información importante para todos los usuarios de Teams. Es una forma rápida y cómoda de que los usuarios de Teams tengan acceso a las actualizaciones con tan solo un clic en una pestaña.

Tenga en cuenta que el proceso que se muestra **debe usar** un sitio o una página de SharePoint *modernos* para funcionar. Este proceso no está disponible para páginas y sitios *clásicos*.

> [!IMPORTANT]
> Asegúrese de que la carga lateral de aplicaciones de Teams está habilitada para su espacio empresarial. Según lo avanzado que se encuentre el proceso de migración del portal de administración de Teams, es posible que tenga que habilitarlo en Teams > Administrador o, en la versión anterior del portal, en Administrador > Configuración > Servicios y complementos > Microsoft Teams > Aplicaciones > Aplicaciones externas.

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Usar App Studio para crear una aplicación independiente de SharePoint Online

Antes de empezar:

1. Tendrá que conocer la dirección URL de un sitio o una página de grupo o de comunicación de SharePoint Online moderno.
    - Estos sitios siempre incluirán */teams/* o */sites/* en sus rutas de acceso.

2. Tendrá que conocer el subdominio de su espacio empresarial, que se usará en el marcador de posición **{{subdomain}}**.

3. Este artículo usará el marcador de posición **{{siteUrl}}** para la *dirección URL* del sitio o la página que haya elegido.
    - Ejemplo de *direcciones URL*:   https://contoso.sharepoint.com/teams/Contoso   *o* https://contoso.sharepoint.com/sites/Contoso
4. Además, se usará **{{sitePath}}** para indicar la *ruta de acceso* de la dirección URL (ej.: /teams/Contoso).
    - Ejemplo de *rutas de acceso*:   /teams/Contoso   *o* /sites/Contoso

En primer lugar, siga estos pasos:

1. Vaya a la tienda de Teams.

2. Instale o abra App Studio.

3. Haga clic en **Abrir**, junto a la opción Aplicación.

4. Con App Studio abierto, haga clic en **Editor de manifiestos**.

5. **Cree una nueva aplicación**.

6. Rellene todos los **Detalles de la aplicación**.

7. Haga clic en **Pestañas** en Capacidades.

8. Haga clic en **Agregar** en la Pestaña personal.

9. Rellene el **Nombre** y elija **un identificador de entidad único nuevo**.

10. Rellene **contentURL y la dirección URL del sitio web**.

- **contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
- **websiteUrl**: {{siteUrl}}

    Ejemplo de **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub

11. Desplácese hasta **Dominios y permisos**. Asegúrese de que la sección dominios válidos contiene el nombre de dominio de SharePoint Online.

    Ejemplo: contoso.sharepoint.com

12. Agregue las siguientes propiedades de **inicio de sesión único** de la aplicación web:

     Ejemplo:  **Id. de aplicación de AAD**: 00000003-0000-0ff1-ce00-000000000000  **Dirección URL de recurso**: {{subdomain}}.sharepoint.com

    ![Realice el inicio de sesión único de la aplicación web, con id. y dirección URL.](media/personal-app.png)

13. **Guarde** estas propiedades y, luego, desplácese hasta **Probar y distribuir**.

14. Instale la aplicación para probar la aplicación personalmente.

> [!IMPORTANT]
> Si no usa Teams App Studio, tendrá que comprimir el archivo manifest.JSON que acaba de crear; vaya a la tienda de aplicaciones de Teams y haga clic en el vínculo **cargar aplicación personalizada** (en la parte inferior derecha de la tienda de aplicaciones). Esto hará que la aplicación esté disponible para usted.

15. Ahora la aplicación está disponible como una pestaña estática para que pueda cargarla y verla en Teams.

## <a name="test-and-view-your-new-static-tab"></a>Probar y ver la nueva pestaña estática

Para ver la nueva pestaña en el escritorio de Teams, desplácese hasta el signo de puntos suspensivos (**...**) en la parte izquierda de la barra de aplicaciones. Buque la nueva aplicación, cargue y pruebe la aplicación independiente en Teams.

Si desea que la nueva aplicación esté disponible en el menú de la izquierda en una posición superior, debe usar una configuración de directiva de aplicaciones. Encontrará esta opción en la sección Administrador de equipo > directiva de aplicaciones > agregar una aplicación anclada. Cuando asigne la directiva a un usuario para realizar pruebas, el cambio se mostrará unas horas más tarde. Teniendo esto en cuenta, decida lo antes posible donde debería aparecer la aplicación para evitar retrasos.

Para ver y probar la nueva aplicación en un dispositivo móvil, abra el cajón de aplicaciones pulsando en la comilla angular (**^**) situada encima de la barra de pestañas de la parte inferior de la pantalla. Busque la aplicación y desplácese hasta ella en el dispositivo móvil.

> [!CAUTION]
> La compatibilidad móvil está actualmente como Versión preliminar para desarrolladores. Para habilitar la Versión preliminar para desarrolladores, vaya a Configuración > Acerca de y, luego, habilite el modo Versión preliminar para desarrolladores.

## <a name="a-sample-manifestjson-file"></a>Ejemplo de archivo Manifest.JSON

El archivo JSON que genere tendrá un aspecto similar al siguiente.

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

            "name": "Contoso Net",

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/",

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet",

            "scopes": [

                "personal"

            ]

        },

        {

            "entityId": "teamSiteTab",

            "name": "Team Contoso",

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/",

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso",

            "scopes": [

                "personal"

            ]

        }

    ],

    "permissions": [

        "identity",

        "messageTeamMembers"

    ],

    "validDomains": [

        "contoso.sharepoint.com"

    ],

    "webApplicationInfo": {

        "id": "00000003-0000-0ff1-ce00-000000000000",

        "resource": "https://contoso.sharepoint.com"

    }

}
```
