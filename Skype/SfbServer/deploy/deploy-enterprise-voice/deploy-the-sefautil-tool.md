---
title: Implementar la herramienta SEFAUtil en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Implementar la herramienta SEFAUtil en Skype Empresarial Server.
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812390"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Implementar la herramienta SEFAUtil en Skype Empresarial
 
Implementar la herramienta SEFAUtil en Skype Empresarial Server.
  
Para implementar y administrar la atención de llamadas grupales, debe usar la versión de Skype Empresarial Server de la herramienta SEFAUtil. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime debe estar instalado en cualquier equipo en el que planee ejecutar la herramienta SEFAUtil. Descárbalo aquí: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). También puede descargar el SDK de UCMA 5, que incluye el tiempo de ejecución, aquí: [SDK de UCMA 5.0.](https://www.microsoft.com/download/details.aspx?id=47345)
  
Puede ejecutar la herramienta SEFAUtil en cualquier grupo de servidores front-end de la implementación. Para ejecutar la herramienta SEFAUtil, debe ejecutar los pasos 1, 2 y 3 desde el Asistente para la implementación de Skype Empresarial en el equipo de la aplicación de confianza. SEFAUtil requiere que el almacén de configuración local esté presente, así como un certificado.
  
> [!NOTE]
> Para obtener más información sobre cómo ejecutar SEFAUtil, consulte el artículo del blog " ¿Cómo hacer[que SEFAutil se ejecute?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implementar SEFAUtil

1. Inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en Permisos de configuración **delegados.**
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
3. La herramienta SEFAUtil solo se puede ejecutar en un equipo que forma parte de un grupo de aplicaciones de confianza. Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de servidores front-end donde planee ejecutar SEFAUtil. En la línea de comandos, ejecute:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN del grupo de servidores: el FQDN del servidor o grupo de servidores que hospedará la aplicación SEFAUtil (normalmente un servidor front-end o grupo de servidores de Skype Empresarial).
    > FQDN del registrador de grupo: el FQDN del servidor front-end de Skype Empresarial o del grupo asociado a este grupo de aplicaciones.
    > Sitio del grupo de servidores: el identificador de sitio del sitio en el que se encuentra este grupo de servidores.

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

6. If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.
    
7. Compruebe que la herramienta SEFAUtil se está ejecutando correctamente, como se muestra a continuación: 
    
    a. Ejecuta la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de reenvío de llamadas de un usuario en la implementación.
    
    b. Muestra la configuración de reenvío de llamadas de un usuario. En la línea de comandos, ejecute:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Se mostrará la configuración de reenvío de llamadas para el usuario.
    

