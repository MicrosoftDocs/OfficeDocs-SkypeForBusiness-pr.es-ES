---
title: Administrar las opciones de configuración del servicio web en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumen: administre las opciones de configuración del servicio web en Skype Empresarial Server.'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806500"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Administrar las opciones de configuración del servicio web en Skype Empresarial Server
 
**Resumen:** Administrar las opciones de configuración del servicio web en Skype Empresarial Server.
  
Puede usar la página **Servicio web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Skype Empresarial Server.
  
Siga estos pasos para crear una nueva directiva de servicio web.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Para crear nuevas opciones de configuración del servicio web

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.
    
4. En la **página Servicio** web, haga clic en **Nuevo** y, a continuación, realice una de las siguientes acciones:
    
   - Para configurar el servicio web para un sitio, haga clic en **Configuración del sitio.** En **Seleccionar un sitio,** haga clic en el sitio al que se aplicará la directiva de servicio web y haga clic en **Aceptar.**
    
   - Para configurar el servicio web para un grupo de servidores, haga clic en **Configuración del grupo de servidores.** En **Seleccionar un servicio,** haga clic en el servicio al que se aplicará la directiva de servicio web y haga clic en **Aceptar.** 
    
5. En **Nueva configuración del servicio web**, en **Autenticación integrada de Windows**, seleccione **Negociar**, **Autenticación integrada de Windows** o **Ninguno.**
    
6. Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
   - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
   - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
   - **Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.
    
7. Haga clic en **Confirmar**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modificar las opciones de configuración existentes del servicio web

Puede usar la página **Servicio web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Skype Empresarial Server.
  
Siga estos pasos para modificar una directiva de servicio web existente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Para modificar las opciones de configuración de servicios web existentes

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.
    
4. En la página **Servicio web**, haga clic en una configuración, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
5. En **Editar configuración de servicio web**, en **Autenticación de Windows**, seleccione **Negociar**, **NTLM** o **Ninguno**.
    
6. Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
   - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
   - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
   - **Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.
    
7. Haga clic en **Confirmar**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Eliminar opciones de configuración de servicio web existentes

Siga estos pasos para eliminar las opciones de configuración del servicio web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Para eliminar las opciones de configuración del servicio web

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.
    
4. En la **página Servicio** web y en el campo de búsqueda, escriba todo o parte del nombre de la directiva que desea eliminar.
    
5. En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.
    
6. Haga clic en **Aceptar**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Eliminación de opciones de configuración del servicio web mediante cmdlets Windows PowerShell web

Puede eliminar las opciones de configuración del servicio web mediante Windows PowerShell y el cmdlet **Remove-CsWebServiceConfiguration.** Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre el uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog "Inicio rápido: administración de [Microsoft Lync Server 2010 con PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Para eliminar una colección específica de opciones de configuración de servicios web

- El siguiente comando quita la configuración de seguridad del servicio web aplicada al sitio Redmond:
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Para eliminar todas las opciones de configuración del servicio web aplicadas al ámbito de sitio

El siguiente comando quita toda la configuración de seguridad del servicio web aplicada al ámbito de servicio:
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Para eliminar todas las opciones de configuración del servicio web que permiten la autenticación de certificados

El siguiente comando quita toda la configuración de seguridad del servicio web que permite el uso de la autenticación de certificados:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Para obtener más información, [vea Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

