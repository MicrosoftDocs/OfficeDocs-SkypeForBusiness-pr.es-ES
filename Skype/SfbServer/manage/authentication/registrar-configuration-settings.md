---
title: Administrar las opciones de configuración de registrador en Skype Empresarial Server
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
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Resumen: administrar las opciones de configuración del registrador para Skype Empresarial Server.'
ms.openlocfilehash: a1cd1048ea37a249126ec892560312a482459d44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119579"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Administrar las opciones de configuración de registrador en Skype Empresarial Server
 
**Resumen:** Administrar las opciones de configuración del registrador para Skype Empresarial Server.
  
Puede usar el registrador para configurar los métodos de autenticación de servidores proxy. El protocolo de autenticación que especifique definirá el tipo de desafío que presentarán los servidores del grupo a los clientes. Los protocolos disponibles son:
  
- **Kerberos** Este es el esquema de autenticación basado en contraseña más seguro disponible para los clientes, pero normalmente solo está disponible para clientes de empresa porque requiere conexión de cliente a un Centro de distribución de claves (controlador de dominio Kerberos). Esta configuración es adecuada si el servidor autentica solo los clientes de empresa.
    
- **NTLM** Esta es la autenticación basada en contraseña disponible para los clientes que usan un esquema de hash de respuesta a desafíos en la contraseña. Esta es la única forma de autenticación disponible para los clientes sin conectividad a un Centro de distribución de claves (controlador de dominio Kerberos), como usuarios remotos. Si un servidor autentica solo usuarios remotos, debe elegir NTLM.
    
- **Autenticación de certificados** Este es el nuevo método de autenticación cuando el servidor necesita obtener certificados de clientes de Lync Phone Edition, teléfonos de área común, Skype Empresarial y la aplicación de la Tienda Windows de Lync. En los clientes de Lync Phone Edition, después de que un usuario inicia sesión y se autentica correctamente proporcionando un número de identificación personal (PIN), Skype Empresarial Server aprovisiona el URI de SIP en el teléfono y aprovisiona un certificado firmado de Skype Empresarial Server o un certificado de usuario que identifica Joe (por ejemplo: SN=joe@contoso.com ) al teléfono. Este certificado se usa para la autenticación con el registrador y los Servicios web.
    
> [!NOTE]
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos. 
  
Si vas a usar clientes de aplicaciones de la Tienda Windows de Lync, debes habilitar la autenticación de certificados.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Para crear nuevas opciones de configuración de registrador

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.
    
4. En la página **Registrador**, haga clic en **Nuevo**.
    
5. En **Seleccionar un servicio**, haga clic en el servicio al que se aplicará el Registrador y, a continuación, haga clic en **Aceptar**.
    
6. En **Nueva configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las funciones de los clientes y la compatibilidad de su entorno:
    
   - **Habilitar autenticación Kerberos**: para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
   - **Habilitar autenticación NTLM**: para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
   - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
7. Haga clic en **Confirmar**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Modificar las opciones de configuración de registrador existentes

Puede usar el registrador para configurar los protocolos de autenticación del servidor proxy. 
  
> [!NOTE]
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos. 
  
Siga los pasos a continuación para modificar un registrador existente. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>Para modificar las opciones de configuración de registrador existentes

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.
    
4. En la página **Registrador**, haga clic en un servicio, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
5. En **Editar configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno:
    
   - **Habilitar autenticación Kerberos**: para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
   - **Habilitar autenticación NTLM**: para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
   - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
6. Haga clic en **Confirmar**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Para eliminar las opciones de configuración del registrador

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y luego en **Registrador**.
    
4. En la página **Registrador**, en el campo de búsqueda, escriba el nombre completo o parcial del registrador que desea eliminar.
    
5. En la lista, haga clic en el registrador que desee, haga clic en **Editar** y luego en **Eliminar**.
    
6. Haga clic en **Aceptar**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración del registrador mediante Windows PowerShell cmdlets

Puede eliminar las opciones de configuración del registrador mediante Windows PowerShell y el cmdlet **Remove-CsProxyConfiguration.** Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Para quitar un conjunto específico de opciones de configuración de seguridad del registrador

- El siguiente comando quita las opciones de configuración de seguridad del registrador aplicadas al servidor perimetral atl-edge-011.litwareinc.com:
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de seguridad del registrador aplicadas al ámbito de sitio

- El siguiente comando quita todas las opciones de configuración de seguridad del registrador aplicadas al servicio del registrador:
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Para quitar todas las opciones de configuración de seguridad del registrador que permiten la autenticación NTLM

- El siguiente comando elimina todas las opciones de configuración de seguridad del registrador que permiten el uso de NTLM para la autenticación de cliente:
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Para obtener más información, [vea Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
