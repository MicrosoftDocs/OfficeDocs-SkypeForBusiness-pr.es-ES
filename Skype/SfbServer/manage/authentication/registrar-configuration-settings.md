---
title: Administrar la configuración de configuración de registrador en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Resumen: Administrar opciones de configuración de registrador de Skype para Business Server.'
ms.openlocfilehash: fdeca4389ffb64bd68cb3aee7ba6b28e979c5769
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901511"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Administrar la configuración de configuración de registrador en Skype para Business Server
 
**Resumen:** Administrar opciones de configuración de registrador de Skype para Business Server.
  
Puede usar el registrador para configurar los métodos de autenticación de servidores proxy. El protocolo de autenticación que especifique definirá el tipo de desafío que presentarán los servidores del grupo a los clientes. Los protocolos disponibles son:
  
- **Kerberos** Este es el esquema de autenticación basado en contraseñas más seguro disponible para los clientes, pero normalmente solo está disponible para los clientes de empresa, ya que requiere conexión de cliente a un centro de distribución de claves (controlador de dominio de Kerberos). Esta configuración es adecuada si el servidor autentica a sólo clientes de empresa.
    
- **NTLM** Esto es la autenticación basada en contraseñas disponible para los clientes que utilicen un esquema de hash de desafío / respuesta en la contraseña. Esta es la única forma de autenticación disponible para clientes sin conectividad con un centro de distribución de clave (controlador de dominio de Kerberos), por ejemplo, los usuarios remotos. Si un servidor autentica sólo los usuarios remotos, debe elegir NTLM.
    
- **Autenticación de certificados** Este es el método de autenticación de nuevo cuando el servidor necesita obtener certificados de clientes de Lync Phone Edition, teléfonos de área común, Skype para la empresa y la aplicación de la tienda de Windows de Lync. En los clientes de Lync Phone Edition, una vez que un usuario inicia sesión y se autentica correctamente al proporcionar un número de identificación personal (PIN), Skype para Business Server, a continuación, aprovisiona el URI de SIP en el teléfono y aprovisiona una Skype para Business Server firmado certificado o un certificado de usuario que identifica Joe (ej: SN=joe@contoso.com) en el teléfono. Este certificado se usa para autenticarse con el Registrador y los Servicios web.
    
> [!NOTE]
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos. 
  
Si va a usar a los clientes de aplicación de almacenamiento de Windows de Lync, debe habilitar la autenticación de certificados.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Para crear nuevas opciones de configuración de registrador

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.
    
4. En la página **Registrador**, haga clic en **Nuevo**.
    
5. En **Seleccionar un servicio**, haga clic en el servicio al que se aplicará el Registrador y, a continuación, haga clic en **Aceptar**.
    
6. En **Nueva configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las funciones de los clientes y la compatibilidad de su entorno:
    
   - **Habilitar autenticación Kerberos** para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
   - **Habilitar autenticación NTLM** para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
   - **Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
7. Haga clic en **Confirmar**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Modificar opciones de configuración de un registrador existente

Puede usar el registrador para configurar los protocolos de autenticación del servidor proxy. 
  
> [!NOTE]
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos. 
  
Siga los pasos a continuación para modificar un registrador existente. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>Para modificar las opciones de configuración de un registrador existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.
    
4. En la página **Registrador**, haga clic en un servicio, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
5. En **Editar configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno:
    
   - **Habilitar autenticación Kerberos** para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
   - **Habilitar autenticación NTLM** para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
   - **Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
6. Haga clic en **Confirmar**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Para eliminar las opciones de configuración del registrador

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.
    
4. En la página **Registrador**, en el campo de búsqueda, escriba el nombre completo o parcial del registrador que desea eliminar.
    
5. En la lista, haga clic en el registrador que desee, haga clic en **Editar** y luego en **Eliminar**.
    
6. Haga clic en **Aceptar**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de registrador con Cmdlets de Windows PowerShell

Puede eliminar las opciones de configuración de registrador mediante el uso de Windows PowerShell y el cmdlet **Remove-CsProxyConfiguration** . Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Para quitar un conjunto específico de opciones de configuración de seguridad del registrador

- El siguiente comando quita las opciones de configuración de seguridad del registrador aplicadas al servidor perimetral atl-edge-011.litwareinc.com:
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de seguridad del registrador aplicadas al ámbito de sitio

- El siguiente comando quita todas las opciones de configuración de seguridad del registrador aplicadas al servicio del registrador:
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Para quitar todas las opciones de configuración de seguridad del registrador que permiten la autenticación NTLM

- El siguiente comando elimina todas las opciones de configuración de seguridad del registrador que permiten el uso de NTLM para la autenticación de cliente:
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Para obtener información detallada, vea [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  

