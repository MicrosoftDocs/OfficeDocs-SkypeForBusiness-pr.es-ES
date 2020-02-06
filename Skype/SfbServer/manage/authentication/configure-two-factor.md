---
title: Configurar la autenticación en dos fases en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumen: configure la autenticación en dos fases en Skype empresarial Server.'
ms.openlocfilehash: 40749cbe3e0bf50a6ff6a640038d63d4a4479b7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818822"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurar la autenticación en dos fases en Skype empresarial Server

**Resumen:** Configurar la autenticación en dos fases en Skype empresarial Server.

En las siguientes secciones se describen los pasos necesarios para configurar la autenticación en dos fases para la implementación. Para obtener más información sobre la autenticación en dos fases, vea [Habilitar la autenticación multifactor de Office 365 para administradores en línea: publicación de usuario de red](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurar una entidad de certificación raíz empresarial para admitir la autenticación de tarjeta inteligente

En los siguientes pasos, se describe cómo configurar una CA raíz empresarial para admitir la autenticación de tarjeta inteligente:

Para obtener información sobre cómo instalar una entidad emisora de certificados raíz de empresa, vea [instalar una entidad](https://go.microsoft.com/fwlink/p/?LinkID=313364)emisora de certificados raíz de empresa.

1. Inicie sesión en el equipo de la CA empresarial usando una cuenta de administrador de dominio.

2. Inicie el Administrador del sistema y compruebe que está instalado el rol Inscripción web de entidad de certificación.

3. En el menú **Herramientas administrativas**, abra la consola de administración de **Entidad de certificación**.

4. En el panel de navegación, expanda **Entidad de certificación**.

5. Haga clic con el botón derecho en **Plantillas de certificado**, elija **Nueva** y, luego, elija **Plantilla de certificado que se va a emitir**.

6. Elija **Enrollment Agent**, **Usuario de tarjeta inteligente** e **Inicio de sesión de Tarjeta inteligente**.

7. Haga clic en **Aceptar**.

8. Haga clic con el botón derecho en **Plantillas de certificado**.

9. Elija **Administrar**.

10. Abra las propiedades de la plantilla Usuario de tarjeta inteligente.

11. Haga clic en la pestaña **Seguridad**.

12. Cambie los permisos como se indica a continuación:

    - Agregue cuentas de usuario individuales de AD con los permisos Leer/Inscribir (permitir), o

    - Agregue un grupo de seguridad que contenga los usuarios de tarjeta inteligente con permisos Leer/Inscribir (permitir), o

    - Agregue el grupo Usuarios del dominio con los permisos Leer/Inscribir (permitir)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurar Windows 8 para las tarjetas inteligentes virtuales

Un factor que se necesita considerar al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de la implementación. Windows 8 proporciona una serie de nuevas capacidades de seguridad y una de las características nuevas más interesantes es la compatibilidad con las tarjetas inteligentes virtuales.

Para los equipos que vienen con el chip del Módulo de plataforma segura (TPM) que cumple la especificación versión 1.2, las organizaciones ahora pueden obtener beneficios del inicio de sesión con tarjeta inteligente sin hacer inversiones adicionales en hardware. Para obtener más información, consulte [uso de tarjetas inteligentes virtuales con Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar Windows 8 para las tarjetas inteligentes virtuales

1. Inicie sesión en el equipo con Windows 8 con las credenciales de un usuario habilitado para Skype empresarial.

2. En la pantalla de inicio de Windows 8, mueva el cursor a la esquina inferior derecha de la pantalla.

3. Seleccione la opción **Buscar** y, a continuación, busque forCommand petición de datos.

4. Haga clic con el botón derecho en **Símbolo del sistema** y, luego, seleccione **Ejecutar como administrador**.

5. Abra la consola de administración del Módulo de plataforma segura (TPM) ejecutando el siguiente comando:

  ```console
  Tpm.msc
  ```

6. Desde la consola de administración de TPM, compruebe que la versión de la especificación de TPM sea al menos 1.2

    > [!NOTE]
    > Si recibe un diálogo que indique que no se encuentra un Módulo de plataforma segura (TPM) compatible, compruebe que el equipo tenga un módulo TPM compatible y que esté habilitado en el sistema BIOS.

7. Cierre la consola de administración de TPM

8. Desde el símbolo del sistema, cree una tarjeta inteligente virtual por medio del siguiente comando:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Para proporcionar un valor PIN personalizado al crear la tarjeta inteligente virtual, use en su lugar la solicitud de PIN.

9. Desde el símbolo del sistema, abra la consola de administración del equipo ejecutando el siguiente comando:

  ```console
  CompMgmt.msc
  ```

10. En la consola de administración del equipo, seleccione **Administración de dispositivos**.

11. Expanda **Lectores de tarjetas inteligentes**.

12. Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.

## <a name="enroll-users-for-smart-card-authentication"></a>Inscribir a usuarios en la autenticación de tarjeta inteligente

En general, existen dos métodos para inscribir a los usuarios en la autenticación de tarjeta inteligente. El método más sencillo consiste en que los usuarios se inscriban directamente en la autenticación de tarjeta inteligente a través de la inscripción web; el más complejo consiste en usar un Enrollment Agent. Este tema se centra en la autoinscripción para usar certificados de tarjeta inteligente.

Para obtener más información sobre la inscripción en nombre de los usuarios como agente de inscripción, consulte [inscribirse para certificados en nombre de otros usuarios](https://go.microsoft.com/fwlink/p/?LinkID=313367).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Para inscribir a usuarios en la autenticación de tarjeta inteligente

1. Inicie sesión en la estación de trabajo Windows 8 con las credenciales de un usuario habilitado para Skype empresarial.

2. Inicie Internet Explorer.

3. Vaya a la página de **inscripción Web de la entidad emisora de certificados** (por ejemplo, https://MyCA.contoso.com/certsrv).

    > [!NOTE]
    > Si usa Internet Explorer 10, puede que tenga que ver este sitio web en modo de compatibilidad.

4. En la página **principal**, elija **Solicitar un certificado**.

5. Luego elija **Solicitud avanzada**.

6. Elija **Crear y enviar una solicitud a esta CA**.

7. Seleccione **Usuario de tarjeta inteligente** en la sección **Plantilla de certificado** y complete la solicitud de certificado avanzada con los siguientes valores:

  - En **Opciones de clave**, confirme la siguiente configuración:

    - Active el botón de radio **Crear conjunto de claves nuevo**.

    - En **CSP**, seleccione **Proveedor base de cifrado para tarjetas inteligentes de Microsoft**.

    - En **Uso de la clave**, seleccione **Exchange** (es la única opción disponible).

    - En **Tamaño de la clave**, escriba 2048.

    - Confirme que está activado **Nombre automático de contenedor de claves**.

    - Deje las demás casillas desactivadas.

  - En **Opciones adicionales**, confirme los siguientes valores:

    - En **Formato de la solicitud**, seleccione **CMC**.

    - En **Algoritmo hash**, seleccione **sha1**.

    - Para el certificado de enterSmardcard de **nombre descriptivo** .

8. Si utiliza un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.

9. Haga clic en **Enviar** para enviar la solicitud de certificado.

10. Cuando se le pida, escriba el PIN que se usó para crear la tarjeta inteligente virtual.

    > [!NOTE]
    > El valor PIN predeterminado de la tarjeta inteligente virtual es ' 12345678 '.

11. Una vez emitido el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.

    > [!NOTE]
    >  Si la solicitud de certificado da el error "este explorador Web no admite la generación de solicitudes de certificado", hay tres formas posibles de resolver el problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurar los Servicios de federación de Active Directory (AD FS 2.0)

En la siguiente sección se describe cómo configurar los servicios de federación de Active Directory (AD FS 2.0) para admitir autenticación multifactor. Para obtener más información sobre cómo instalar 2,0 de AD FS, consulte [instrucciones paso a paso y guías de ad fs 2,0](https://go.microsoft.com/fwlink/p/?LinkId=313374).

> [!NOTE]
> Al instalar AD FS 2.0, no use Windows Server Manager para agregar el rol de los servicios de federación de Active Directory. En su lugar, descargue e instale el [paquete de servicios de Federación de active directory 2,0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375).

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Para configurar AD FS para la autenticación en dos fases

1. Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.

2. Inicie Windows PowerShell.

3. Desde la línea de comandos de Windows PowerShell, ejecute el siguiente comando:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Establezca una asociación con cada uno de los servidores que estarán habilitados para la autenticación pasiva ejecutando el siguiente comando, sustituyendo el nombre del servidor específico para su implementación:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Desde el menú Herramientas administrativas, inicie la consola de administración de AD FS 2.0.

6. Expanda **relaciones** > de confianza**confianzas**de usuario de confianza.

7. Compruebe que se ha creado una nueva confianza para su servidor de Skype empresarial.

8. Cree y asigne una regla de autorización de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Cree y asigne una regla de transformación de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Desde la consola de administración de AD FS 2.0, haga clic con el botón secundario en la relación de confianza para el usuario autenticado y seleccione **Editar reglas de notificaciones**.

11. Seleccione la pestaña **Reglas de autorización de emisión** y compruebe que la nueva regla de autorización se haya creado correctamente.

12. Seleccione la pestaña **Reglas de transformación de emisión** y compruebe que la nueva regla de transformación se haya creado correctamente.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configurar AD FS 2.0 para que sea compatible con la autenticación de clientes

Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita autenticación con tarjetas inteligentes:

- Autenticación basada en formularios (FBA)

- Autenticación de cliente de seguridad de capa de transporte

Al usar la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse ya sea por medio de su nombre de usuario/contraseña o por medio de su tarjeta inteligente y PIN. Este tema se enfoca en cómo implementar la autenticación de cliente de seguridad de capa de transporte con AD FS 2.0. Para obtener más información sobre los tipos de autenticación 2,0 de AD FS, consulte [ad fs 2,0: Cómo cambiar el tipo de autenticación local](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Para configurar AD FS 2.0 para admitir la autenticación de cliente

1. Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.

2. Inicie Windows Explorer.

3. Vaya a C:\inetpub\adfs\ls.

4. Haga una copia de seguridad del archivo web.config existente.

5. Abra el archivo web.config existente con el Bloc de notas.

6. Desde la barra de menús, seleccione **Editar** y, luego, seleccione **Buscar**.

7. Busque \<localAuthenticationTypes\>.

    Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.

8. Mueva la línea que contiene el tipo de autenticación TLSClient hacia la parte superior de la lista en la sección.

9. Guarde y cierre el archivo web.config.

10. Inicie un símbolo del sistema con privilegios elevados.

11. Reinicie IIS ejecutando el siguiente comando:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configurar la autenticación pasiva de Skype Empresarial Server

En la siguiente sección se describe cómo configurar Skype empresarial Server para admitir la autenticación pasiva. Una vez habilitado, los usuarios que tengan habilitada la autenticación en dos fases deberán usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión con el cliente de Skype empresarial.

> [!NOTE]
> Se recomienda encarecidamente a los clientes que habiliten la autenticación pasiva del registrador y los servicios web en el nivel de servicios. Si se habilita la autenticación pasiva del registrador y los servicios web en el nivel global, lo más probable es que se produzcan errores de autenticación en toda la organización cuando los usuarios no inicien sesión con el cliente de escritorio compatible.

### <a name="web-service-configuration"></a>Configuración de servicios web

En los siguientes pasos, se describe cómo crear una configuración de servicios web personalizada para los Directores, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Para crear una configuración de servicios web personalizada

1. Inicie sesión en el servidor front-end de Skype empresarial Server con una cuenta de administrador de Skype empresarial.

2. Inicie el shell de administración de Skype empresarial Server.

3. Desde la línea de comandos del shell de administración de Skype empresarial Server, cree una nueva configuración de servicio web para cada director, grupo de servidores Enterprise y servidor Standard Edition que se habilitará para la autenticación pasiva ejecutando el siguiente comando:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > El valor del FQDN WsFedPassiveMetadataUri es el Nombre del servicio de federación de su servidor AD FS 2.0. El valor de Nombre del servicio de federación se puede consultar en la consola de administración de AD FS 2.0 al hacer clic en **Servicio** en el panel de navegación y, luego, elegir **Editar propiedades del servicio de federación**.

4. Para comprobar que los valores de UseWsFedPassiveAuth y WsFedPassiveMetadataUri se configuraron correctamente, ejecute el siguiente comando:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. En los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de WebTicket. Para todos los directores, grupos empresariales y servidores Standard Edition que se habilitarán para la autenticación pasiva, todos los demás tipos de autenticación deben estar deshabilitados en los servicios Web de Skype empresarial ejecutando el siguiente cmdlet:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación, ejecute el siguiente cmdlet:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuración de proxy

Cuando la autenticación de certificados está deshabilitada para los servicios Web de Skype empresarial, el cliente de Skype empresarial usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticar el servicio de registro. La autenticación de certificado se sigue necesitando para permitir al cliente que recupere un WebTicket, pero Kerberos y NTLM tienen que estar deshabilitados en el servicio registrador.

En los siguientes pasos, se describe cómo crear una configuración de proxy personalizada para los grupos de servidores perimetrales, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Para crear una configuración de proxy personalizada

1. Desde la línea de comandos del shell de administración de Skype empresarial Server, cree una nueva configuración de proxy para cada grupo de servidores perimetrales de Skype para empresas, grupo de servidores Enterprise y servidor Standard Edition que se habilitará para la autenticación pasiva mediante la ejecución de lo siguiente comandos

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación de proxy, ejecute el siguiente comando:

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Vea también

[Administrar la autenticación en dos fases en Skype empresarial Server](two-factor-authentication.md)

[Usar la autenticación en dos fases con el cliente de Skype empresarial y Skype empresarial Server](use-two-factor.md)
