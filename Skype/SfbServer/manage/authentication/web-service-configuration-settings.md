---
title: Administrar la configuración de configuración del servicio Web en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumen: Administrar opciones de configuración del servicio Web en Skype para Business Server.'
ms.openlocfilehash: 53d709c9964a665c97ba809ca6f40dceb0be137b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884107"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Administrar la configuración de configuración del servicio Web en Skype para Business Server
 
**Resumen:** Administrar opciones de configuración del servicio Web en Skype para Business Server.
  
Puede usar la página **Servicio Web** para configurar los métodos de autenticación para obtener acceso a Skype para Business Server relacionados con servidores web y servicios Web.
  
Siga estos pasos para crear una nueva directiva de servicios web.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Para crear opciones de configuración nuevas para un servicio web

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad**y, a continuación, en **Servicio web**.
    
4. En la página **Servicio web**, haga clic en **Nuevo** y, a continuación, realice una de las siguientes acciones:
    
   - Para configurar el servicio web para un sitio, haga clic en **Configuración del sitio**. En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva de servicios web y, a continuación, haga clic en **Aceptar**.
    
   - Para configurar el servicio web para un grupo de servidores, haga clic en **Configuración del grupo de servidores**. En **Seleccionar un servicio**, haga clic en el servicio al que se aplicará la directiva de servicios web y, a continuación, haga clic en **Aceptar**. 
    
5. En **Nueva configuración de servicio web**, en **Autenticación de Windows**, seleccione **Negociar**, **Autenticación de Windows Integrada** o **Ninguna**.
    
6. Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
   - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
   - **Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
   - **Habilitar descarga de cadena de certificados** para que los servidores a los que se presente un certificado de autenticación descarguen la cadena de certificados para ese certificado.
    
7. Haga clic en **Confirmar**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modificar opciones de configuración de un servicio web existente

Puede usar la página **Servicio Web** para configurar los métodos de autenticación para obtener acceso a Skype para Business Server relacionados con servidores web y servicios Web.
  
Siga estos pasos para modificar una directiva de servicio web existente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Para modificar opciones de configuración de un servicio web existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad**y, a continuación, en **Servicio web**.
    
4. En la página **Servicio web**, haga clic en una configuración, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
5. En **Editar configuración de servicio web**, en **Autenticación de Windows integrada**, seleccione **Negociar**, **NTLM** o **Ninguna**.
    
6. Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
   - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
   - **Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
   - **Habilitar descarga de cadena de certificados** para que los servidores a los que se presente un certificado de autenticación descarguen la cadena de certificados para ese certificado.
    
7. Haga clic en **Confirmar**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Modificar opciones de configuración de un servicio web existente

Siga estos pasos para eliminar opciones de configuración de un servicio web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Para eliminar opciones de configuración de un servicio web existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad**y, a continuación, en **Servicio web**.
    
4. En la página **Servicio web**, vaya al campo de búsqueda y escriba total o parcialmente el nombre de la directiva que desea eliminar.
    
5. En la lista de directivas, haga clic en la directiva que desea, en **Editar** y, a continuación, en **Eliminar**.
    
6. Haga clic en **Aceptar**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Eliminación de opciones de configuración del servicio Web mediante el uso de Cmdlets de Windows PowerShell

Puede eliminar la configuración del servicio web mediante el uso de Windows PowerShell y el cmdlet **Remove-CsWebServiceConfiguration** . Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Para eliminar una colección específica de valores de configuración de los servicios web:

- El comando siguiente quita los valores de seguridad de los servicios web que se aplican al sitio de Redmond:
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Para eliminar todas las opciones de configuración de los servicios web que se aplican al ámbito del sitio

El comando siguiente quita todos los valores de seguridad de los servicios web que se aplican al ámbito del sitio:
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Para eliminar todas las opciones de configuración de los servicios web que permiten la autenticación de certificados

El comando siguiente quita todos los valores de seguridad de los servicios web que permiten el uso de la autenticación de certificados:
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Para obtener más información, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

