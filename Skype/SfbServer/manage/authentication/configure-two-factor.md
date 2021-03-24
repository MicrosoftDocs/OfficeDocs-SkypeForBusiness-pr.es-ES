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
ms.openlocfilehash: 8651be3fbc07bb890637bc8d1c7c99a827d1ea1e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096826"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurar la autenticación en dos fases en Skype Empresarial Server

**Resumen:** Configure la autenticación en dos fases en Skype Empresarial Server.

En las secciones siguientes se describen los pasos necesarios para configurar la autenticación en dos fases para la implementación. Para obtener más información acerca de la autenticación en dos [fases, vea Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurar una entidad de certificación raíz de empresa para admitir la autenticación de tarjeta inteligente

Los siguientes pasos describen cómo configurar una CA raíz de empresa para admitir la autenticación de tarjeta inteligente:

Para obtener información sobre cómo instalar una ENTIDAD de certificación raíz de empresa, vea [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).

1. Inicie sesión en el equipo de ca de empresa con una cuenta de administrador de dominio.

2. Inicie el Administrador del sistema y compruebe que el rol de inscripción web de entidad de certificación está instalado.

3. En el **menú Herramientas administrativas,** abra la consola **de administración de entidad de** certificación.

4. En el panel navegación, expanda **Entidad de certificación**.

5. Haga clic con el botón **secundario en Plantillas de** certificado , seleccione **Nuevo** y, a continuación, seleccione Plantilla de certificado **para emitir**.

6. Seleccione **Agente de inscripción,** **Usuario de tarjeta inteligente** e Inicio de sesión de **tarjeta inteligente.**

7. Haga clic en **Aceptar**.

8. Haga clic con el botón secundario **en Plantillas de certificado**.

9. Seleccione **Administrar**.

10. Abra las propiedades de la plantilla Usuario de tarjeta inteligente.

11. Haga clic en la **pestaña** Seguridad.

12. Cambie los permisos de la siguiente manera:

    - Agregar cuentas de AD de usuario individuales con permisos de lectura/inscripción (permitir) o

    - Agregar un grupo de seguridad que contenga usuarios de tarjetas inteligentes con permisos de lectura/inscripción (permitir) o

    - Agregar el grupo Usuarios de dominio con permisos de lectura/inscripción (permitir)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurar Windows 8 para tarjetas inteligentes virtuales

Un factor a tener en cuenta al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de implementación. Windows 8 proporciona una serie de nuevas funcionalidades de seguridad y una de las nuevas características más interesantes es la compatibilidad con tarjetas inteligentes virtuales.

Para los equipos equipados con un chip de módulo de plataforma segura (TPM) que cumple con la versión 1.2 de la especificación, las organizaciones ahora pueden obtener las ventajas del inicio de sesión con tarjeta inteligente sin realizar ninguna inversión adicional en hardware. Para obtener más información, consulta [Usar tarjetas inteligentes virtuales con Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar Windows 8 para tarjetas inteligentes virtuales

1. Inicie sesión en el equipo con Windows 8 con las credenciales de un usuario habilitado para Skype Empresarial.

2. En la pantalla Inicio de Windows 8, mueve el cursor a la esquina inferior derecha de la pantalla.

3. Seleccione la **opción Buscar** y, a continuación, busque Símbolo del sistema.

4. Haga clic con el **botón secundario en símbolo del** sistema y, a continuación, seleccione Ejecutar como **administrador**.

5. Abra la consola de administración del módulo de plataforma segura (TPM) ejecutando el siguiente comando:

  ```console
  Tpm.msc
  ```

6. Desde la consola de administración de TPM, compruebe que la versión de especificación del TPM es al menos 1.2

    > [!NOTE]
    > Si recibe un cuadro de diálogo que indica que no se puede encontrar un módulo de plataforma de confianza compatible (TPM), compruebe que el equipo tiene un módulo TPM compatible y que está habilitado en el BIOS del sistema.

7. Cerrar la consola de administración de TPM

8. Desde el símbolo del sistema, cree una nueva tarjeta inteligente virtual con el siguiente comando:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Para proporcionar un valor de PIN personalizado al crear la tarjeta inteligente virtual, use /pin prompt en su lugar.

9. En el símbolo del sistema, abra la consola de administración de equipos ejecutando el siguiente comando:

  ```console
  CompMgmt.msc
  ```

10. En la consola administración del equipo, seleccione **Administración de dispositivos**.

11. Expanda **Lectores de tarjetas inteligentes**.

12. Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.

## <a name="enroll-users-for-smart-card-authentication"></a>Inscribir usuarios para la autenticación con tarjeta inteligente

Por lo general, hay dos métodos para inscribir usuarios para la autenticación de tarjetas inteligentes. El método más sencillo implica que los usuarios se inscriban directamente para la autenticación de tarjetas inteligentes mediante la inscripción web, mientras que el método más complejo implica el uso de un agente de inscripción. Este tema se centra en la inscripción automática para certificados de tarjeta inteligente.

Para obtener más información sobre la inscripción en nombre de los usuarios como agente de inscripción, vea Inscribir para certificados [en nombre de otros usuarios](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Para inscribir usuarios para autenticación con tarjeta inteligente

1. Inicie sesión en la estación de trabajo de Windows 8 con las credenciales de un usuario habilitado para Skype Empresarial.

2. Inicie Internet Explorer.

3. Vaya a la **página Inscripción web de entidad de** certificación (por ejemplo, https://MyCA.contoso.com/certsrv) .

    > [!NOTE]
    > Si usa Internet Explorer 10, es posible que deba ver este sitio web en modo de compatibilidad.

4. En la **página de** bienvenida, seleccione Solicitar **un certificado**.

5. A continuación, **seleccione Solicitud avanzada**.

6. Seleccione **Crear y enviar una solicitud a esta CA**.

7. Seleccione **Usuario de tarjeta inteligente en** la sección Plantilla **de** certificado y complete la solicitud de certificado avanzada con los siguientes valores:

  - **Las opciones clave** confirman que sigue la configuración:

    - Seleccione el **botón de opción Crear nuevo conjunto de** teclas

    - Para **CSP,** seleccione Proveedor criptográfico **de tarjeta inteligente de Microsoft Base**

    - Para **Uso de clave,** **seleccione Exchange** (esta es la única opción disponible).

    - Para **Tamaño de clave**, escriba 2048

    - Confirmar que **el nombre del contenedor de claves automático** está seleccionado

    - Deje las otras casillas desactivadas.

  - En **Opciones adicionales,** confirme los siguientes valores:

    - Para **Formato de solicitud,** **seleccione CMC**.

    - Para **Algoritmo hash,** seleccione **sha1**.

    - Para **Nombre descriptivo,** escribaSmardcard Certificate.

8. Si usas un lector de tarjeta inteligente física, inserta la tarjeta inteligente en el dispositivo.

9. Haga **clic en Enviar** para enviar la solicitud de certificado.

10. Cuando se le pida, escriba el PIN que se usó para crear la tarjeta inteligente virtual.

    > [!NOTE]
    > El valor predeterminado del PIN de tarjeta inteligente virtual es "12345678".

11. Una vez emitido el certificado, haga clic **en Instalar este certificado** para completar el proceso de inscripción.

    > [!NOTE]
    >  Si se produce un error en la solicitud de certificado con el error "Este explorador web no admite la generación de solicitudes de certificado", hay tres maneras posibles de resolver el problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurar servicios de federación de Active Directory (AD FS 2.0)

En la siguiente sección se describe cómo configurar los Servicios de federación de Active Directory (AD FS 2.0) para admitir la autenticación multifactor. Para obtener información sobre cómo instalar AD FS 2.0, vea [AD FS 2.0 Step-by-Step y How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).

> [!NOTE]
> Al instalar AD FS 2.0, no use el Administrador de Windows Server para agregar el rol Servicios de federación de Active Directory. En su lugar, descargue e instale el paquete de Servicios de federación [de Active Directory 2.0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375).

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

5. En el menú Herramientas administrativas, inicie la consola de administración de AD FS 2.0.

6. Expande **Relaciones de confianza**  >  **Confianzas de usuario de confianza**.

7. Compruebe que se ha creado una nueva confianza para su Skype Empresarial Server.

8. Cree y asigne una regla de autorización de emisión para su confianza de usuario de confianza Windows PowerShell mediante la ejecución de los siguientes comandos:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Cree y asigne una regla de transformación de emisión para su confianza de usuario de confianza mediante Windows PowerShell mediante la ejecución de los siguientes comandos:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. En la consola de administración de AD FS 2.0, haga clic con el botón secundario en su confianza de usuario de confianza y seleccione **Editar reglas de notificación.**

11. Seleccione la **pestaña Reglas de autorización de** emisión y compruebe que la nueva regla de autorización se creó correctamente.

12. Seleccione la **pestaña Reglas de transformación de** emisión y compruebe que la nueva regla de transformación se creó correctamente.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configuración de AD FS 2.0 para admitir la autenticación de cliente

Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita la autenticación con tarjetas inteligentes:

- Autenticación basada en formularios (FBA)

- Autenticación de cliente de seguridad de la capa de transporte

Con la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse con su nombre de usuario o contraseña o con su tarjeta inteligente y PIN. Este tema se centra en cómo implementar la autenticación de cliente de seguridad de la capa de transporte con AD FS 2.0. Para obtener más información acerca de los tipos de autenticación de AD FS 2.0, vea [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Para configurar AD FS 2.0 para admitir la autenticación de cliente

1. Inicie sesión en el equipo de AD FS 2.0 con una cuenta de administrador de dominio.

2. Inicie Windows Explorer.

3. Vaya a C:\inetpub\adfs\ls

4. Realice una copia de seguridad del archivo web.config existente.

5. Abra el archivo web.config con el Bloc de notas.

6. En la barra de menús, **seleccione Editar** y, a continuación, **seleccione Buscar**.

7. Buscar \<localAuthenticationTypes\> .

    Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.

8. Mueva la línea que contiene el tipo de autenticación TLSClient a la parte superior de la lista de la sección.

9. Guarde y cierre el web.config archivo.

10. Inicie un símbolo del sistema con privilegios elevados.

11. Reinicie IIS ejecutando el siguiente comando:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configuración de la autenticación pasiva de Skype Empresarial Server

En la siguiente sección se describe cómo configurar Skype Empresarial Server para admitir la autenticación pasiva. Una vez habilitado, los usuarios habilitados para la autenticación en dos fases tendrán que usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión con el cliente de Skype Empresarial.

> [!NOTE]
> Se recomienda encarecidamente que los clientes habiliten la autenticación pasiva para registrar y los servicios web en el nivel de servicio. Si la autenticación pasiva está habilitada para registrador y servicios web en el nivel global, probablemente provocará errores de autenticación en toda la organización para los usuarios que no inicien sesión con el cliente de escritorio compatible.

### <a name="web-service-configuration"></a>Configuración del servicio web

En los pasos siguientes se describe cómo crear una configuración de servicio web personalizada para directores, grupos de servidores de empresa y servidores Standard Edition que se habilitarán para la autenticación pasiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Para crear una configuración de servicio web personalizada

1. Inicie sesión en el servidor front-end de Skype Empresarial Server con una cuenta de administrador de Skype Empresarial.

2. Inicie el Shell de administración de Skype Empresarial Server.

3. Desde la línea de comandos del Shell de administración de Skype Empresarial Server, cree una nueva configuración de servicio web para cada servidor director, grupo de empresas y Standard Edition que se habilitará para la autenticación pasiva ejecutando el siguiente comando:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > El valor del FQDN WsFedPassiveMetadataUri es el nombre del servicio de federación del servidor de AD FS 2.0. El valor nombre del servicio de federación se puede encontrar en la Consola de administración de AD FS 2.0 haciendo clic con el botón secundario en **Servicio** en el panel de navegación y, a continuación, seleccionando Editar propiedades del servicio **de federación**.

4. Compruebe que los valores UseWsFedPassiveAuth y WsFedPassiveMetadataUri se han establecido correctamente ejecutando el siguiente comando:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Para los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de webticket. Para todos los servidores directores, grupos de servidores de empresa y Standard Edition que se habilitarán para la autenticación pasiva, todos los demás tipos de autenticación deben deshabilitarse en Skype Empresarial Web Services ejecutando el siguiente cmdlet:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Compruebe que todos los demás tipos de autenticación se han deshabilitado correctamente ejecutando el siguiente cmdlet:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuración de proxy

Cuando la autenticación de certificados está deshabilitada para Skype Empresarial Web Services, el cliente de Skype Empresarial usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticarse en el servicio de registrador. La autenticación de certificados sigue siendo necesaria para permitir que el cliente recupere un webticket, sin embargo, Kerberos y NTLM deben deshabilitarse para el servicio de registrador.

En los pasos siguientes se describe cómo crear una configuración de proxy personalizada para grupos de servidores perimetrales, grupos de servidores empresariales y servidores Standard Edition que se habilitarán para la autenticación pasiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Para crear una configuración de proxy personalizada

1. Desde la línea de comandos del Shell de administración de Skype Empresarial Server, cree una nueva configuración de proxy para cada grupo perimetral de Skype Empresarial Server, grupo de servidores empresarial y servidor Standard Edition que se habilitará para la autenticación pasiva ejecutando los siguientes comandos:

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Compruebe que todos los demás tipos de autenticación de proxy se han deshabilitado correctamente ejecutando el siguiente comando:

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Ver también

[Administrar la autenticación en dos fases en Skype Empresarial Server](two-factor-authentication.md)

[Usar la autenticación en dos fases con el cliente de Skype Empresarial y Skype Empresarial Server](use-two-factor.md)