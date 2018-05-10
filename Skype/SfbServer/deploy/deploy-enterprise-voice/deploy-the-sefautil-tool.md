---
title: Implementar la herramienta SEFAUtil en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implementación de la herramienta de SEFAUtil de Skype para Business Server.
ms.openlocfilehash: 48fa0077315169e6a80e65e91d7ce9a31583cdb5
ms.sourcegitcommit: 4e9574c8a9eac270135684aa4a8b77621aa46403
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>Implementar la herramienta SEFAUtil en Skype Empresarial 2015
 
Implementación de la herramienta de SEFAUtil de Skype para Business Server.
  
Para implementar y administrar recogida de llamadas de grupo, debe usar el Skype para la versión de la herramienta SEFAUtil Business Server. 
  
> [!IMPORTANT]
> Tiempo de ejecución de Microsoft Unified Communications Managed API (UCMA) 5 debe estar instalado en cualquier equipo donde va a ejecutar la herramienta SEFAUtil. Descargarlo aquí: [Unified Communications Managed API 5.0 en tiempo de ejecución](https://www.microsoft.com/en-us/download/details.aspx?id=47344). También puede descargar el SDK de 5 de UCMA, que incluye el tiempo de ejecución, aquí: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Puede ejecutar la herramienta de SEFAUtil de cualquier grupo de servidores Front-End en su implementación.
  
> [!NOTE]
> Para obtener más información acerca de cómo ejecutar SEFAUtil, vea el artículo del blog de Technet, "[cómo obtener SEFAutil ejecutando?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implementar SEFAUtil

1. Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegar permisos de instalación**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es necesario, definir un grupo de servidores de aplicaciones de confianza para el grupo de servidores Front-End donde va a ejecutar SEFAUtil. En la línea de comandos, ejecute:
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. Defina la herramienta SEFAUtil como aplicación de confianza. En la línea de comandos, ejecute:
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Si es preciso, puede usar otro puerto. 
  
5. Habilite la topología con los cambios. En la línea de comandos, ejecute:
    
  ```
  Enable-CsTopology
  ```

6. Si no lo ha hecho ya, descargue el Skype para la versión de la herramienta SEFAUtil Business Server desde [esta ubicación](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instale en el grupo de aplicaciones de confianza que creó en el paso 3.
    
7. Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica: 
    
    a. Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.
    
    b. Muestre la configuración de reenvío de llamadas de un usuario. En la línea de comandos, ejecute:
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

Aparecerá la configuración de reenvío de llamadas del usuario.
    

