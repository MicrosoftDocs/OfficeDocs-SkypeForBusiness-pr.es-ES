---
title: Configuración de autenticación de dos factores en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumen: Configurar la autenticación de dos factores en Skype para Business Server.'
ms.openlocfilehash: d9df5072e1d67e46c40e1fd82ec1d88354321577
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887249"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configuración de autenticación de dos factores en Skype para Business Server

**Resumen:** Configuración de autenticación de dos factores en Skype para Business Server.

En las siguientes secciones se describen los pasos necesarios para configurar la autenticación en dos fases para la implementación. Para obtener más información acerca de la autenticación en dos fases, vea [autenticación multifactor de habilitación de Office 365 para administradores online - Post del usuario de cuadrícula](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurar una entidad de certificación raíz empresarial para admitir la autenticación de tarjeta inteligente

En los siguientes pasos, se describe cómo configurar una CA raíz empresarial para admitir la autenticación de tarjeta inteligente:

Para obtener información sobre cómo instalar una entidad de certificación raíz de empresa, vea [instalar una entidad de certificación raíz de empresa](https://go.microsoft.com/fwlink/p/?LinkID=313364).

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

Un factor que se necesita considerar al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de la implementación. Windows 8 proporciona un número de nuevas capacidades de seguridad y una de las nuevas características más interesantes es la compatibilidad para tarjetas inteligentes virtuales.

Para los equipos que vienen con el chip del Módulo de plataforma segura (TPM) que cumple la especificación versión 1.2, las organizaciones ahora pueden obtener beneficios del inicio de sesión con tarjeta inteligente sin hacer inversiones adicionales en hardware. Para obtener más información, vea [uso de Virtual las tarjetas inteligentes con Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar Windows 8 para las tarjetas inteligentes virtuales

1. Inicie sesión el equipo de Windows 8 con las credenciales de un Skype para usuario habilitado para el negocio.

2. En la pantalla de inicio de Windows 8, mueva el cursor a la esquina inferior derecha de la pantalla.

3. Seleccione la opción de **búsqueda** y, a continuación, busque forCommand símbolo del sistema.

4. Haga clic con el botón derecho en **Símbolo del sistema** y, luego, seleccione **Ejecutar como administrador**.

5. Abra la consola de administración del Módulo de plataforma segura (TPM) ejecutando el siguiente comando:

  ```
  Tpm.msc
  ```

6. Desde la consola de administración de TPM, compruebe que la versión de la especificación de TPM sea al menos 1.2

    > [!NOTE]
    > Si recibe un diálogo que indique que no se encuentra un Módulo de plataforma segura (TPM) compatible, compruebe que el equipo tenga un módulo TPM compatible y que esté habilitado en el sistema BIOS.

7. Cierre la consola de administración de TPM

8. Desde el símbolo del sistema, cree una tarjeta inteligente virtual por medio del siguiente comando:

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Para proporcionar un valor PIN personalizado al crear la tarjeta inteligente virtual, use en su lugar la solicitud de PIN.

9. Desde el símbolo del sistema, abra la consola de administración del equipo ejecutando el siguiente comando:

  ```
  CompMgmt.msc
  ```

10. En la consola de administración del equipo, seleccione **Administración de dispositivos**.

11. Expanda **Lectores de tarjetas inteligentes**.

12. Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.

## <a name="enroll-users-for-smart-card-authentication"></a>Inscribir a usuarios en la autenticación de tarjeta inteligente

En general, existen dos métodos para inscribir a los usuarios en la autenticación de tarjeta inteligente. El método más sencillo consiste en que los usuarios se inscriban directamente en la autenticación de tarjeta inteligente a través de la inscripción web; el más complejo consiste en usar un Enrollment Agent. Este tema se centra en la autoinscripción para usar certificados de tarjeta inteligente.

Para obtener más información sobre inscribirse en nombre de los usuarios como un agente de inscripción, vea [inscripción de certificados en nombre de otros usuarios](https://go.microsoft.com/fwlink/p/?LinkID=313367).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Para inscribir a usuarios en la autenticación de tarjeta inteligente

1. Inicie sesión en la estación de trabajo de Windows 8 con las credenciales de un Skype para usuario habilitado para el negocio.

2. Inicie Internet Explorer.

3. Vaya a la página de **Inscripción de certificado de entidad de certificación Web** (por ejemplo, https://MyCA.contoso.com/certsrv).

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

    - Para **Nombre descriptivo** enterSmardcard certificado.

8. Si utiliza un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.

9. Haga clic en **Enviar** para enviar la solicitud de certificado.

10. Cuando se le pida, escriba el PIN que se usó para crear la tarjeta inteligente virtual.

    > [!NOTE]
    > El valor PIN de tarjeta inteligente virtual predeterminado es '12345678'.

11. Una vez emitido el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.

    > [!NOTE]
    >  Si la solicitud de certificado produce el error "este explorador Web no admite la generación de las solicitudes de certificados", hay tres maneras posibles para resolver el problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurar los Servicios de federación de Active Directory (AD FS 2.0)

En la siguiente sección se describe cómo configurar los servicios de federación de Active Directory (AD FS 2.0) para admitir autenticación multifactor. Para obtener información acerca de cómo instalar AD FS 2.0, vea [AD FS 2.0 Step y cómo a las guías](https://go.microsoft.com/fwlink/p/?LinkId=313374).

> [!NOTE]
> Al instalar AD FS 2.0, no use Windows Server Manager para agregar el rol de los servicios de federación de Active Directory. En su lugar, descargue e instale el [paquete de Active Directory Federation Services 2.0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375).

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Para configurar AD FS para la autenticación en dos fases

1. Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.

2. Inicie Windows PowerShell.

3. Desde la línea de comandos de Windows PowerShell, ejecute el siguiente comando:

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Establezca una asociación con cada uno de los servidores que estarán habilitados para la autenticación pasiva ejecutando el siguiente comando, sustituyendo el nombre del servidor específico para su implementación:

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Desde el menú Herramientas administrativas, inicie la consola de administración de AD FS 2.0.

6. Expanda **las relaciones de confianza** > **confía en el usuario de confianza**.

7. Compruebe que se ha creado una nueva relación de confianza para su Skype para Business Server.

8. Cree y asigne una regla de autorización de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Cree y asigne una regla de transformación de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Desde la consola de administración de AD FS 2.0, haga clic con el botón secundario en la relación de confianza para el usuario autenticado y seleccione **Editar reglas de notificaciones**.

11. Seleccione la pestaña **Reglas de autorización de emisión** y compruebe que la nueva regla de autorización se haya creado correctamente.

12. Seleccione la pestaña **Reglas de transformación de emisión** y compruebe que la nueva regla de transformación se haya creado correctamente.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configurar AD FS 2.0 para que sea compatible con la autenticación de clientes

Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita autenticación con tarjetas inteligentes:

- Autenticación basada en formularios (FBA)

- Autenticación de cliente de seguridad de capa de transporte

Al usar la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse ya sea por medio de su nombre de usuario/contraseña o por medio de su tarjeta inteligente y PIN. Este tema se enfoca en cómo implementar la autenticación de cliente de seguridad de capa de transporte con AD FS 2.0. Para obtener más información acerca de los tipos de autenticación 2.0 de AD FS, vea [AD FS 2.0: cómo cambiar el tipo de autenticación Local](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Para configurar AD FS 2.0 para admitir la autenticación de cliente

1. Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.

2. Inicie Windows Explorer.

3. Vaya a C:\inetpub\adfs\ls.

4. Haga una copia de seguridad del archivo web.config existente.

5. Abra el archivo web.config existente con el Bloc de notas.

6. Desde la barra de menús, seleccione **Editar** y, luego, seleccione **Buscar**.

7. Buscar \<localAuthenticationTypes\>.

    Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.

8. Mueva la línea que contiene el tipo de autenticación TLSClient hacia la parte superior de la lista en la sección.

9. Guarde y cierre el archivo web.config.

10. Inicie un símbolo del sistema con privilegios elevados.

11. Reinicie IIS ejecutando el siguiente comando:

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configurar la autenticación pasiva de Skype Empresarial Server

En la siguiente sección se describe cómo configurar Skype para Business Server admitir la autenticación pasiva. Una vez habilitado, los usuarios que están habilitados para la autenticación en dos fases se necesitarán para usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión mediante el Skype para clientes empresariales.

> [!NOTE]
> Se recomienda encarecidamente a los clientes que habiliten la autenticación pasiva del registrador y los servicios web en el nivel de servicios. Si se habilita la autenticación pasiva del registrador y los servicios web en el nivel global, lo más probable es que se produzcan errores de autenticación en toda la organización cuando los usuarios no inicien sesión con el cliente de escritorio compatible.

### <a name="web-service-configuration"></a>Configuración de servicios web

En los siguientes pasos, se describe cómo crear una configuración de servicios web personalizada para los Directores, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Para crear una configuración de servicios web personalizada

1. Inicie sesión en su Skype para servidor de negocio de servidor Front-End mediante un Skype para la cuenta de administrador de empresa.

2. Inicie el Skype para Shell de administración de servidor empresarial.

3. Desde Skype para Business Server Management Shell de línea de comandos, cree una nueva configuración de servicio Web para cada Director, grupo de servidores Enterprise y servidores Standard Edition que va a estar habilitada para autenticación pasiva, ejecute el comando siguiente:

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > El valor del FQDN WsFedPassiveMetadataUri es el Nombre del servicio de federación de su servidor AD FS 2.0. El valor de Nombre del servicio de federación se puede consultar en la consola de administración de AD FS 2.0 al hacer clic en **Servicio** en el panel de navegación y, luego, elegir **Editar propiedades del servicio de federación**.

4. Para comprobar que los valores de UseWsFedPassiveAuth y WsFedPassiveMetadataUri se configuraron correctamente, ejecute el siguiente comando:

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. En los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de WebTicket. Para todos los directores, grupos de servidores Enterprise y servidores Standard Edition que va a estar habilitados para la autenticación de pasivo, todos los demás tipos de autenticación deben estar deshabilitados en Skype para los servicios Web empresarial ejecutando el siguiente cmdlet:

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación, ejecute el siguiente cmdlet:

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuración de proxy

Cuando está deshabilitada la autenticación de certificados de Skype para los servicios Web empresarial, la Skype para clientes empresariales usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticarse en el servicio de registrador. La autenticación de certificado se sigue necesitando para permitir al cliente que recupere un WebTicket, pero Kerberos y NTLM tienen que estar deshabilitados en el servicio registrador.

En los siguientes pasos, se describe cómo crear una configuración de proxy personalizada para los grupos de servidores perimetrales, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Para crear una configuración de proxy personalizada

1. Desde Skype para Business Server Management Shell de línea de comandos, cree una nueva configuración de proxy para cada Skype para servidor perimetral de servidores de negocio, grupo de servidores Enterprise y Standard Edition que va a estar habilitado para autenticación pasiva mediante la ejecución de la siguiente comandos:

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación de proxy, ejecute el siguiente comando:

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Consulte también

[Administrar la autenticación de dos factores en Skype para Business Server](two-factor-authentication.md)

[Usar autenticación de dos factores con Skype para clientes empresariales y Skype para Business Server](use-two-factor.md)
