---
title: Implementar la herramienta SEFAUtil en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implementar la herramienta SEFAUtil en Skype empresarial Server.
ms.openlocfilehash: 1721f4d611a08a3054366e36b0ec9a3ebccf6c78
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245392"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Implementar la herramienta SEFAUtil en Skype empresarial
 
Implementar la herramienta SEFAUtil en Skype empresarial Server.
  
Para implementar y administrar la recogida de llamadas grupales, debes usar la versión de Skype para empresas Server de la herramienta SEFAUtil. 
  
> [!IMPORTANT]
> El tiempo de ejecución de la API administrada de comunicaciones unificadas de Microsoft (UCMA) 5 debe instalarse en cualquier equipo en el que tenga previsto ejecutar la herramienta SEFAUtil. Descárguela aquí: [API administrada de comunicaciones unificadas de 5,0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344). También puede descargar el SDK de UCMA 5, que incluye el tiempo de ejecución, aquí: [UCMA 5,0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Puede ejecutar la herramienta SEFAUtil en cualquier grupo de servidores front-end de su implementación. Para ejecutar la herramienta SEFAUtil, debe ejecutar los pasos 1, 2 y 3 del asistente de implementación de Skype empresarial en el equipo de aplicaciones de confianza. SEFAUtil requiere que el almacén de configuración local esté presente, así como un certificado.
  
> [!NOTE]
> Para obtener más información sobre cómo ejecutar SEFAUtil, consulte el artículo del blog, "[Cómo obtener SEFAUtil Running](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implementar SEFAUtil

1. Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en **permisos de configuración de delegado**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de servidores front-end en el que tiene previsto ejecutar SEFAUtil. En la línea de comandos, ejecute:
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN del Grupo: el nombre completo del servidor o grupo de servidores que va a hospedar la aplicación de SEFAUtil (generalmente un servidor o grupo de servidores front-end de Skype empresarial).
    > FQDN del registrador de grupos: el FQDN del servidor front-end de Skype empresarial o del grupo de servidores asociado a este grupo de aplicaciones.
    > Sitio de Grupo: el identificador de sitio del sitio en el que se aloja este grupo.

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

6. Si todavía no lo ha hecho, descargue la versión de Skype empresarial Server de la herramienta SEFAUtil desde [esta ubicación](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instálela en el grupo de aplicaciones de confianza que creó en el paso 3.
    
7. Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica: 
    
    a. Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.
    
    b. Muestre la configuración de reenvío de llamadas de un usuario. En la línea de comandos, ejecute:
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Aparecerá la configuración de reenvío de llamadas del usuario.
    

