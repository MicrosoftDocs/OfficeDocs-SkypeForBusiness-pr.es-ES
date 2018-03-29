---
title: Implementar la herramienta SEFAUtil en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantación de la herramienta SEFAUtil en Skype para Business Server.
ms.openlocfilehash: eba4c6d9c6d0c48256621537350a822c3314ca40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>Implementar la herramienta SEFAUtil en Skype Empresarial 2015
 
Implantación de la herramienta SEFAUtil en Skype para Business Server.
  
Para implementar y administrar grupo llamar recogida, necesitará utilizar el Skype para la versión de la herramienta SEFAUtil Business Server. 
  
> [!IMPORTANT]
> Instale el SDK de la API administrada de comunicaciones unificadas (UCMA) de Microsoft 3.0 Core en los equipos donde planee ejecutar la herramienta SEFAUtil. 
  
Puede ejecutar la herramienta SEFAUtil en cualquier grupo de Front-End de su implementación.
  
> [!NOTE]
> Para obtener más información acerca de cómo ejecutar SEFAUtil, consulte el artículo del blog de Technet "[cómo obtener SEFAutil ejecutando?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implementar SEFAUtil

1. Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de Front-End donde piensa ejecutar SEFAUtil. En la línea de comandos, ejecute:
    
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

6. Si no lo ha hecho ya, descargar el Skype para la versión de la herramienta SEFAUtil Business Server desde [esta ubicación](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instalar en el grupo de aplicaciones de confianza creó en el paso 3.
    
7. Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica: 
    
    a. Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.
    
    b. Muestre la configuración de reenvío de llamadas de un usuario. En la línea de comandos, ejecute:
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

Aparecerá la configuración de reenvío de llamadas del usuario.
    

