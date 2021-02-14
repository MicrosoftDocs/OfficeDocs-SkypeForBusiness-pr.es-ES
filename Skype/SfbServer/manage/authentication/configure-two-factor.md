---
title: Configurar la autenticación en dos fases en Skype Empresarial Server
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
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumen: configure la autenticación en dos fases en Skype Empresarial Server.'
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814420"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurar la autenticación en dos fases en Skype Empresarial Server

**Resumen:** Configure la autenticación en dos fases en Skype Empresarial Server.

En las secciones siguientes se describen los pasos necesarios para configurar la autenticación en dos fases para la implementación. Para obtener más información acerca de la autenticación en dos fases, vea Habilitar la autenticación multifactor de [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=313332)para administradores en línea: publicación de usuario de cuadrícula.

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurar una entidad de certificación raíz de empresa para admitir la autenticación con tarjeta inteligente

Los siguientes pasos describen cómo configurar una CA raíz de empresa para admitir la autenticación de tarjeta inteligente:

Para obtener información sobre cómo instalar una ENTIDAD de certificación raíz de empresa, vea [Instalar una entidad de certificación raíz de empresa.](https://go.microsoft.com/fwlink/p/?LinkID=313364)

1. Inicie sesión en el equipo de ca de empresa con una cuenta de administrador de dominio.

2. Inicie el Administrador del sistema y compruebe que esté instalado el rol inscripción web de entidad de certificación.

3. En el **menú Herramientas administrativas,** abra la consola **de administración de la entidad** de certificación.

4. En el panel de navegación, expanda **Entidad de certificación.**

5. Haga clic con el **botón secundario en Plantillas de** certificado, seleccione **Nuevo** y, a continuación, seleccione Plantilla de certificado **para emitir.**

6. Seleccione **Agente de inscripción,** **Usuario de tarjeta inteligente** e Inicio de sesión de **tarjeta inteligente.**

7. Haga clic en **Aceptar**.

8. Haga clic con el botón secundario en **Plantillas de certificado.**

9. Seleccione **Administrar**.

10. Abra las propiedades de la plantilla Usuario de tarjeta inteligente.

11. Haga clic en la **pestaña** Seguridad.

12. Cambie los permisos de la siguiente manera:

    - Agregar cuentas de AD de usuario individuales con permisos de lectura/inscripción (permitir) o

    - Agregar un grupo de seguridad que contenga usuarios de tarjetas inteligentes con permisos de lectura/inscripción (permitir) o

    - Agregar el grupo Usuarios de dominio con permisos de lectura/inscripción (permitir)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurar Windows 8 para tarjetas inteligentes virtuales

Un factor que se debe tener en cuenta al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de implementación. Windows 8 proporciona una serie de nuevas funcionalidades de seguridad y una de las características nuevas más interesantes es la compatibilidad con tarjetas inteligentes virtuales.

En el caso de los equipos equipados con un chip del Módulo de plataforma segura (TPM) que cumple la versión 1.2 de la especificación, las organizaciones ahora pueden obtener las ventajas del inicio de sesión con tarjeta inteligente sin realizar inversiones adicionales en hardware. Para obtener más información, vea [Usar tarjetas inteligentes virtuales con Windows 8.](https://go.microsoft.com/fwlink/p/?LinkId=313365)

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar Windows 8 para tarjetas inteligentes virtuales

1. Inicie sesión en el equipo con Windows 8 con las credenciales de un usuario habilitado para Skype Empresarial.

2. En la pantalla Inicio de Windows 8, mueve el cursor a la esquina inferior derecha de la pantalla.

3. Seleccione la **opción de** búsqueda y, a continuación, busque El símbolo del sistema.

4. Haga clic con el **botón secundario en el símbolo** del sistema y, a continuación, seleccione Ejecutar como **administrador.**

5. Abra la consola de administración del Módulo de plataforma segura (TPM) ejecutando el siguiente comando:

  ```console
  Tpm.msc
  ```

6. Desde la consola de administración de TPM, comprueba que la versión de especificación del TPM sea al menos 1.2

    > [!NOTE]
    > Si recibes un cuadro de diálogo que indica que no se encuentra un módulo de plataforma de confianza compatible (TPM), comprueba que el equipo tiene un módulo TPM compatible y que está habilitado en el BIOS del sistema.

7. Cerrar la consola de administración de TPM

8. Desde el símbolo del sistema, cree una nueva tarjeta inteligente virtual con el siguiente comando:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Para proporcionar un valor de PIN personalizado al crear la tarjeta inteligente virtual, use el símbolo del sistema /pin en su lugar.

9. Desde el símbolo del sistema, abra la consola de administración de equipos ejecutando el siguiente comando:

  ```console
  CompMgmt.msc
  ```

10. En la consola de administración de equipos, seleccione **Administración de dispositivos.**

11. Expanda **lectores de tarjetas inteligentes.**

12. Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.

## <a name="enroll-users-for-smart-card-authentication"></a>Inscribir usuarios para la autenticación con tarjeta inteligente

Por lo general, existen dos métodos para inscribir usuarios para la autenticación con tarjeta inteligente. El método más sencillo implica que los usuarios se inscriban directamente para la autenticación de tarjetas inteligentes mediante la inscripción web, mientras que el método más complejo implica el uso de un agente de inscripción. Este tema se centra en la inscripción automática para certificados de tarjeta inteligente.

Para obtener más información sobre la inscripción en nombre de los usuarios como agente de inscripción, consulta Inscribirse para certificados [en nombre de otros usuarios.](https://go.microsoft.com/fwlink/p/?LinkID=313367)

### <a name="to-enroll-users-for-smart-card-authentication"></a>Para inscribir usuarios para la autenticación con tarjeta inteligente

1. Inicie sesión en la estación de trabajo de Windows 8 con las credenciales de un usuario habilitado para Skype Empresarial.

2. Inicia Internet Explorer.

3. Vaya a la **página Inscripción web de** entidad de certificación (por ejemplo, https://MyCA.contoso.com/certsrv)

    > [!NOTE]
    > Si usas Internet Explorer 10, es posible que debas ver este sitio web en modo de compatibilidad.

4. En la **página principal,** seleccione **Solicitar un certificado.**

5. A continuación, seleccione **Solicitud avanzada.**

6. Seleccione **Crear y envíe una solicitud a esta CA.**

7. Seleccione **Usuario de tarjeta inteligente en** la sección Plantilla **de** certificado y complete la solicitud de certificado avanzada con los siguientes valores:

  - **Las opciones clave** confirman que sigue la configuración:

    - Seleccionar el **botón de opción Crear nuevo conjunto de** teclas

    - Para **CSP,** seleccione **Proveedor criptográfico de tarjeta inteligente base de Microsoft**

    - Para **Uso de claves,** **seleccione Exchange** (esta es la única opción disponible).

    - En **Tamaño de clave,** escriba 2048

    - Confirmar que **está seleccionado el nombre del contenedor de claves** automáticas

    - Deje las otras casillas desactivadas.

  - En **Opciones adicionales,** confirme los siguientes valores:

    - En **Formato de solicitud,** **seleccione CMC**.

    - Para **algoritmo hash,** seleccione **sha1**.

    - En **Nombre descriptivo,** escriba Certificado de TarjetaSmardcard.

8. Si usa un lector de tarjeta inteligente física, inserte la tarjeta inteligente en el dispositivo.

9. Haga **clic en** Enviar para enviar la solicitud de certificado.

10. Cuando se le solicite, escriba el PIN que se usó para crear la tarjeta inteligente virtual.

    > [!NOTE]
    > El valor predeterminado del PIN de la tarjeta inteligente virtual es "12345678".

11. Una vez emitido el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.

    > [!NOTE]
    >  Si se produce un error en la solicitud de certificado con el error "Este explorador web no admite la generación de solicitudes de certificado", hay tres formas posibles de resolver el problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configuración de servicios de federación de Active Directory (AD FS 2.0)

En la siguiente sección se describe cómo configurar los Servicios de federación de Active Directory (AD FS 2.0) para admitir la autenticación multifactor. Para obtener información sobre cómo instalar AD FS 2.0, vea las guías paso a paso de [AD FS 2.0 y cómo hacerlo.](https://go.microsoft.com/fwlink/p/?LinkId=313374)

> [!NOTE]
> Al instalar AD FS 2.0, no use el Administrador de Windows Server para agregar el rol servicios de federación de Active Directory. En su lugar, descargue e instale el paquete de Servicios de federación [de Active Directory 2.0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375).

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Para configurar AD FS para la autenticación en dos fases

1. Inicie sesión en el equipo de AD FS 2.0 con una cuenta de administrador de dominio.

2. Iniciar Windows PowerShell

3. Desde la Windows PowerShell de comandos, ejecute el siguiente comando:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Establezca una asociación con cada servidor que se habilitará para la autenticación pasiva ejecutando el siguiente comando, reemplazando el nombre del servidor específico de la implementación:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. En el menú Herramientas administrativas, inicia la consola de administración de AD FS 2.0.

6. Expanda **Relaciones de confianza relaciones** de confianza de usuario de  >  **confianza.**

7. Compruebe que se ha creado una nueva confianza para su Skype Empresarial Server.

8. Cree y asigne una regla de autorización de emisión para su relación de confianza para usuario autenticado mediante Windows PowerShell ejecutando los siguientes comandos:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Crea y asigna una regla de transformación de emisión para tu relación de confianza para usuario autenticado mediante Windows PowerShell ejecutando los siguientes comandos:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. En la consola de administración de AD FS 2.0, haga clic con el botón secundario en la confianza del usuario de confianza y seleccione **Editar reglas de notificación.**

11. Seleccione la pestaña **Reglas de autorización de** emisión y compruebe que la nueva regla de autorización se haya creado correctamente.

12. Selecciona la pestaña **Reglas de transformación de** emisión y comprueba que la nueva regla de transformación se creó correctamente.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configuración de AD FS 2.0 para admitir la autenticación de cliente

Existen dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita la autenticación mediante tarjetas inteligentes:

- Autenticación basada en formularios (FBA)

- Autenticación de cliente de seguridad de la capa de transporte

Mediante la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse con su nombre de usuario o contraseña o con su tarjeta inteligente y PIN. Este tema se centra en cómo implementar la autenticación de cliente de seguridad de la capa de transporte con AD FS 2.0. Para obtener más información acerca de los tipos de autenticación de AD FS 2.0, vea [AD FS 2.0: Cómo](https://go.microsoft.com/fwlink/p/?LinkId=313384)cambiar el tipo de autenticación local.

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Para configurar AD FS 2.0 para admitir la autenticación de cliente

1. Inicie sesión en el equipo de AD FS 2.0 con una cuenta de administrador de dominio.

2. Inicie Windows Explorer.

3. Vaya a C:\inetpub\adfs\ls

4. Realice una copia de seguridad del archivo web.config existente.

5. Abra el archivo de web.config existente mediante el Bloc de notas.

6. En la barra de menús, **seleccione Editar** y, a continuación, **seleccione Buscar**.

7. Buscar \<localAuthenticationTypes\> .

    Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.

8. Mueva la línea que contiene el tipo de autenticación TLSClient a la parte superior de la lista de la sección.

9. Guarde y cierre el archivo web.config archivo.

10. Inicia un símbolo del sistema con privilegios elevados.

11. Reinicie IIS ejecutando el siguiente comando:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configuración de la autenticación pasiva de Skype Empresarial Server

En la siguiente sección se describe cómo configurar Skype Empresarial Server para admitir la autenticación pasiva. Una vez habilitado, los usuarios habilitados para la autenticación en dos fases tendrán que usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión con el cliente de Skype Empresarial.

> [!NOTE]
> Se recomienda encarecidamente que los clientes habiliten la autenticación pasiva para el registrador y los servicios web en el nivel de servicio. Si la autenticación pasiva está habilitada para el registrador y los servicios web en el nivel global, es probable que se den como resultado errores de autenticación en toda la organización para los usuarios que no inician sesión con el cliente de escritorio compatible.

### <a name="web-service-configuration"></a>Configuración del servicio web

Los siguientes pasos describen cómo crear una configuración de servicio web personalizada para directores, grupos de servidores enterprise y servidores Standard Edition que se habilitarán para la autenticación pasiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Para crear una configuración de servicio web personalizada

1. Inicie sesión en el servidor front-end de Skype Empresarial Server con una cuenta de administrador de Skype Empresarial.

2. Inicie el Shell de administración de Skype Empresarial Server.

3. Desde la línea de comandos del Shell de administración de Skype Empresarial Server, cree una nueva configuración de servicio web para cada director, grupo de servidores enterprise y servidor Standard Edition que se habilitará para la autenticación pasiva ejecutando el siguiente comando:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > El valor del FQDN WsFedPassiveMetadataUri es el nombre de servicio de federación del servidor de AD FS 2.0. El valor nombre del servicio de federación se puede encontrar en la Consola de administración de AD FS 2.0 haciendo clic con el botón secundario en **Servicio** en el panel de navegación y, a continuación, seleccionando Editar propiedades del servicio de **federación.**

4. Compruebe que los valores UseWsFedPassiveAuth y WsFedPassiveMetadataUri se han establecido correctamente ejecutando el siguiente comando:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Para los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de webticket. Para todos los directores, grupos de servidores enterprise y servidores Standard Edition que se habilitarán para la autenticación pasiva, todos los demás tipos de autenticación deben deshabilitarse en los servicios web de Skype Empresarial ejecutando el siguiente cmdlet:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Compruebe que todos los demás tipos de autenticación se hayan deshabilitado correctamente ejecutando el siguiente cmdlet:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuración de proxy

Cuando la autenticación de certificados está deshabilitada para los servicios web de Skype Empresarial, el cliente de Skype Empresarial usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticarse en el servicio de registrador. La autenticación de certificados sigue siendo necesaria para permitir que el cliente recupere un webticket, pero kerberos y NTLM deben deshabilitarse para el servicio de registrador.

Los siguientes pasos describen cómo crear una configuración de proxy personalizada para grupos de servidores perimetrales, grupos de servidores empresariales y servidores Standard Edition que se habilitarán para la autenticación pasiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Para crear una configuración de proxy personalizada

1. Desde la línea de comandos del Shell de administración de Skype Empresarial Server, cree una nueva configuración de proxy para cada grupo de servidores perimetrales de Skype Empresarial Server, grupo de servidores enterprise y servidor Standard Edition que se habilitará para la autenticación pasiva mediante la ejecución de los siguientes comandos:

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Para comprobar que todos los demás tipos de autenticación de proxy se han deshabilitado correctamente, ejecute el siguiente comando:

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Vea también

[Administrar la autenticación en dos fases en Skype Empresarial Server](two-factor-authentication.md)

[Usar la autenticación en dos fases con el cliente de Skype Empresarial y Skype Empresarial Server](use-two-factor.md)
