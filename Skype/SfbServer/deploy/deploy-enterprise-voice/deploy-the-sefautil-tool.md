---
title: Implementar la herramienta SEFAUtil en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Deploying The SEFAUtil Tool in Skype for Business Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986815"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Implementar la herramienta SEFAUtil en Skype empresarial
 
Deploying The SEFAUtil Tool in Skype for Business Server.
  
Para implementar y administrar la recogida de llamadas de grupo, debe usar la versión de Skype empresarial Server de la herramienta SEFAUtil. 
  
> [!IMPORTANT]
> El tiempo de ejecución de la API administrada de comunicaciones unificadas de Microsoft (UCMA) 5 debe instalarse en cualquier equipo en el que se vaya a ejecutar la herramienta SEFAUtil. Descárguelo aquí: [API administrada de comunicaciones unificadas 5,0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). También puede descargar el SDK de UCMA 5, que incluye el tiempo de ejecución, aquí: [UCMA 5,0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Puede ejecutar la herramienta SEFAUtil en cualquier grupo de servidores front-end de su implementación. Para ejecutar la herramienta SEFAUtil debe ejecutar los pasos 1, 2 y 3 del Asistente para la implementación de Skype empresarial en el equipo de la aplicación de confianza. SEFAUtil requiere que esté presente el almacén de configuración local, así como un certificado.
  
> [!NOTE]
> Para obtener más información sobre cómo ejecutar SEFAUtil, vea el artículo del blog "[How to get SEFAUtil Running?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implementar SEFAUtil

1. Inicie sesión en el equipo donde esté instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en **Delegate Setup Permissions**.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
    
3. La herramienta SEFAUtil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de servidores front-end en el que planea ejecutar SEFAUtil. En la línea de comandos, ejecute:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN del grupo de servidores: el FQDN del servidor o grupo de servidores que va a hospedar la aplicación de SEFAUtil (normalmente un grupo o un servidor front-end de Skype empresarial).
    > FQDN del registrador de grupo de servidores: el FQDN del servidor front-end o grupo de servidores front-end de Skype empresarial asociado con este grupo de aplicaciones.
    > Sitio de Grupo: el identificador de sitio del sitio en el que se hospeda este grupo de servidores.

4. Defina la herramienta SEFAUtil como una aplicación de confianza. En la línea de comandos, ejecute:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Puede usar un puerto diferente si es necesario. 
  
5. Habilite la topología con los cambios. En la línea de comandos, ejecute:
    
   ```powershell
   Enable-CsTopology
   ```

6. Si todavía no lo ha hecho, descargue la versión de Skype empresarial Server de la herramienta SEFAUtil desde [esta ubicación](https://www.microsoft.com/download/details.aspx?id=52631)e instálela en el grupo de aplicaciones de confianza que creó en el paso 3.
    
7. Compruebe que la herramienta SEFAUtil se está ejecutando correctamente, de la siguiente manera: 
    
    a. Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación.
    
    b. Muestra la configuración de desvío de llamadas de un usuario. En la línea de comandos, ejecute:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Se mostrará la configuración de desvío de llamadas para el usuario.
    

