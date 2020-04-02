---
title: Crear una aplicación del portal de intranet de un equipo "desde un sitio o una página de SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Tome un sitio o página de SharePoint Online y cree una pestaña estática independiente que se puede usar como un portal de intranet para su organización.
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106637"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Crear una aplicación del portal de intranet de un equipo "desde un sitio o una página de SharePoint Online

Siga los pasos descritos en este artículo para crear una aplicación independiente y estática dentro de teams que se vincule al sitio de intranet de su organización.

Se crea una *aplicación personal de Teams* de su sitio de intranet de SharePoint y aparecerá como una pestaña dentro de Teams. Esta pestaña puede contener información importante para todos los usuarios de su equipo. Es una forma rápida y cómoda para que los usuarios de Teams accedan a las actualizaciones con un solo clic.

Tenga en cuenta que el proceso que se muestra **debe usar** un sitio o página de SharePoint *moderno* para trabajar. Este proceso no está disponible para sitios o páginas *clásicas* .

> [!IMPORTANT]
> Asegúrese de que la carga de las aplicaciones de Teams está habilitada para su inquilino. En función de dónde se encuentre en el proceso de migración del portal de administración de Teams, es posible que tenga que habilitarlo en Teams > admin, o en la configuración de > de administrador > servicios y complementos > aplicaciones de Microsoft Teams > > aplicaciones externas, en la versión anterior del portal. 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Usar App Studio para crear una aplicación independiente de SharePoint Online
' ' ' Antes de empezar:
1. Tendrá que conocer la dirección URL de una comunicación moderna de SharePoint Online o un sitio de grupo o página.
    - Estos sitios siempre tendrán */equipos/* o */sites/* en sus rutas.

2. Necesitará conocer el subdominio del inquilino, que se usará en el marcador de posición **{{subdominio}}**.

3. En este artículo se usará el marcador de posición **{{siteUrl}}** como *dirección URL* del sitio o página que elija.
    - *Direcciones URL*de https://contoso.sharepoint.com/teams/Contosoejemplo: *o*   https://contoso.sharepoint.com/sites/Contoso 
4. Además, se usará **{{sitePath}}** para indicar la ruta de *acceso* de la dirección URL (por ejemplo:/Teams/contoso).
    - *Rutas*de ejemplo:/Teams/contoso *o* /sites/contoso 

Empiece siguiendo los pasos siguientes:

1. Vaya a la tienda de Teams.

2. Instale o abra App Studio.

3. Haga clic en **abrir**, junto a la opción aplicación.

4. Con App Studio abierto, haga clic en el **Editor de manifiestos**.

5. **Crear una nueva aplicación**.

6. Rellene todos los detalles de la **aplicación**.

7. En capacidades, haga clic en **pestañas** .

8. Haga clic en **Agregar** en la pestaña personal.

9. Rellene el **nombre** y elija **un nuevo identificador de entidad única**.

10. Rellene el **contentURL y la dirección URL del sitio web**. 

- **contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}  
- **web'iteUrl**: {{siteUrl}} ' ' ejemplo **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. Vaya a **dominios y Permissi'ns**. Asegúrese de que la sección dominios válidos contiene el nombre de dominio de SharePoint Online.
' ' Ejemplo: contoso.sharepoint.com

12. Agregue las siguientes propiedades de **Inicio de sesión único** de la aplicación web: ' ' ejemplo: ' ' ' ' identificador de la **aplicación AAD**: **URL del recurso**00000003-0000-0ff1-ce00-000000000000: {{subdominio}}. ![SharePoint. com ' ' ' Inicio de sesión único con el identificador y la dirección URL.](media/personal-app.png)

13. **Guarde** estas propiedades y, a continuación, vaya a **probar y distribuir**. 

14. Instale la aplicación para probar personalmente la aplicación.

> [!IMPORTANT]
> Si no usa Teams App Studio, tendrá que. zip el manifiesto. Archivo JSON que acaba de crear, navegue hasta el App Store en Teams y haga clic en el vínculo **cargar aplicación personalizada** (en la parte inferior derecha de la App Store). Esto hará que la aplicación esté disponible para usted.

15. Ahora la aplicación está disponible como una pestaña estática para que la cargue y la vea en Teams.

## <a name="test-and-view-your-new-static-tab"></a>Probar y ver la nueva ficha estática

Para ver la nueva pestaña en el escritorio de Teams, navegue hasta los puntos suspensivos (**...**) en el lado izquierdo de la barra de la aplicación. Busque su nueva aplicación, cargarla y pruebe su aplicación independiente en Teams.

Si desea que la nueva aplicación esté disponible en el menú de la izquierda en una posición superior, debe usar una configuración de directiva de aplicación. Esta opción puede encontrarse en la sección administrador de grupo > Directiva de aplicación > agregar una aplicación anclada. Cuando asigne la Directiva a un usuario para realizar pruebas, el cambio aparecerá 24 horas más tarde. Teniendo esto en mente, decida dónde debe aparecer la aplicación en la primera comodidad para ayudar a evitar retrasos.

Para ver y probar la nueva aplicación en un dispositivo móvil, abra el alimentador de aplicaciones pulsando en la comilla angular (**^**) situada encima de la barra de pestañas situada cerca de la parte inferior de la pantalla. Busque la aplicación y desplácese hasta ella en el dispositivo móvil.
        
> [!CAUTION]
> La compatibilidad con teléfonos móviles está actualmente en Developer Preview. Para habilitar Developer Preview, ve a configuración > acerca de y habilita el modo de vista previa para desarrolladores.

## <a name="a-sample-manifestjson-file"></a>Un archivo manifest. JSON de ejemplo

El archivo JSO que generes tendrá un aspecto similar al siguiente.

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
''
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