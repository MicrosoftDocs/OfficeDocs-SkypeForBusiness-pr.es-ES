---
title: Administrar la configuración de la configuración de registrar en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Resumen: administrar la configuración de la configuración de registrar para Skype empresarial Server.'
ms.openlocfilehash: 4ad7815da0744a78cd72208ef390362bff26c2ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291175"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Administrar la configuración de la configuración de registrar en Skype empresarial Server
 
**Resumen:** Administrar la configuración de la configuración del registrador de Skype empresarial Server.
  
Puede usar el registrador para configurar los métodos de autenticación de servidores proxy. El protocolo de autenticación que especifique definirá el tipo de desafío que presentarán los servidores del grupo a los clientes. Los protocolos disponibles son:
  
- **Kerberos** Este es el esquema de autenticación basado en contraseñas más seguro disponible para los clientes, pero normalmente solo está disponible para clientes de empresa, ya que requiere conexión de cliente a un centro de distribución de claves (controlador de dominio de Kerberos). Esta configuración es adecuada si el servidor autentica solo clientes de empresa.
    
- **NTLM** Esta es la autenticación basada en contraseña disponible para los clientes que usan un esquema de hash de desafío/respuesta en la contraseña. Esta es la única forma de autenticación disponible para los clientes sin conexión a un centro de distribución de claves (controlador de dominio de Kerberos), como los usuarios remotos. Si un servidor autentica solo usuarios remotos, debe elegir NTLM.
    
- **Autenticación de certificados** Este es el método de autenticación nuevo cuando el servidor necesita obtener certificados de clientes de Lync Phone Edition, teléfonos de área común, Skype empresarial y la aplicación de la tienda Windows de Lync. En los clientes de Lync Phone Edition, después de que un usuario inicie sesión y se autentique correctamente proporcionando un número de identificación personal (PIN), Skype empresarial Server le entregará el URI del SIP al teléfono y proporciones un Skype empresarial Server firmado certificado o un certificado de usuario que identifica Joe (por ejemplo: SN=joe@contoso.com) en el teléfono. Este certificado se usa para autenticarse con el Registrador y los Servicios web.
    
> [!NOTE]
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos. 
  
Si va a usar los clientes de la aplicación de la tienda Windows de Lync, debe habilitar la autenticación de certificados.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Para crear nuevas opciones de configuración de registrador

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
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

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.
    
4. En la página **Registrador**, haga clic en un servicio, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
5. En **Editar configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno:
    
   - **Habilitar autenticación Kerberos** para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
   - **Habilitar autenticación NTLM** para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
   - **Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
6. Haga clic en **Confirmar**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Para eliminar las opciones de configuración del registrador

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.
    
4. En la página **Registrador**, en el campo de búsqueda, escriba el nombre completo o parcial del registrador que desea eliminar.
    
5. En la lista, haga clic en el registrador que desee, haga clic en **Editar** y luego en **Eliminar**.
    
6. Haga clic en **Aceptar**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar opciones de configuración de registrar mediante cmdlets de Windows PowerShell

Puede eliminar la configuración del registrador con Windows PowerShell y el cmdlet **Remove-CsProxyConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.
  
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

Para obtener más información, consulte [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  

