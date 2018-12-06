---
title: Implementar la aplicación de la Tienda Windows de Lync
TOCTitle: Implementar la aplicación de la Tienda Windows de Lync
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ822971(v=OCS.15)
ms:contentKeyID: 52061731
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar la aplicación de la Tienda Windows de Lync

 

_**Última modificación del tema:** 2016-12-08_

Antes de poner Aplicación de la Tienda Windows de Lync a disposición de los usuarios, asegúrese de que la implementación cumpla con los [Requisitos de la aplicación de la Tienda Windows de Lync](lync-server-2013-lync-windows-store-app-requirements.md). Para obtener detalles sobre cómo configurar Lync Server 2013 para que admita Aplicación de la Tienda Windows de Lync, consulte el artículo del blog NextHop sobre la Detección automática de Lync Server y la aplicación de la Tienda Windows Lync en [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966). Una vez que ha configurado correctamente el entorno de servidor, podrá indicar a los usuarios que descarguen la aplicación Lync desde la Tienda Windows realizando una búsqueda con el término "Lync".

## Habilitar la autenticación multifactor para Aplicación de la Tienda Windows de Lync

Actualizaciones acumulativas para Lync Server 2013: junio de 2013 agrega compatibilidad con la autenticación multifactor para clientes de Aplicación de la Tienda Windows de Lync. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como una tarjeta inteligente o un PIN, para autenticar a los usuarios externos cuando inician sesión en las reuniones de Lync. Para habilitar la autenticación multifactor, implemente el servidor de federación de los Servicios de federación de Active Directory (AD FS) y habilite la autenticación pasiva en Lync Server 2013. Una vez que ha configurado AD FS, los usuarios externos que intenten unirse a reuniones de Lync verán una página web de autenticación multifactor de AD FS con el desafío de nombre de usuario y contraseña, junto con los demás métodos de autenticación adicionales que haya configurado.

> [!IMPORTANT]  
> A continuación, se incluyen algunas consideraciones importantes para planear la configuración de AD FS para la autenticación multifactor en Aplicación de la Tienda Windows de Lync:
> <ul>
> <li><p>Se requiere como mínimo Lync Server 2013 con Actualizaciones acumulativas para Lync Server 2013: junio de 2013. Los clientes de escritorio de Lync 2013 no necesitan Actualizaciones acumulativas para Lync Server 2013: junio de 2013, por lo que puede parecer que la autenticación pasiva funciona, ya que los clientes de Lync 2013 se pueden autenticar. Pero el proceso de autenticación de los clientes de Aplicación de la Tienda Windows de Lync no se completará correctamente y no se mostrará ningún mensaje de error ni de notificación.</p></li>
> <li><p>Es necesario configurar el servidor de modo que el único tipo de autenticación ofrecido sea la autenticación pasiva.</p></li>
> <li><p>Si usa equilibradores de carga de hardware, habilite la persistencia basada en cookies en los equilibradores de carga, para que todas las solicitudes del cliente de Aplicación de la Tienda Windows de Lync se controlen con el mismo servidor front-end.</p></li>
> <li><p>Al establecer una relación de confianza para usuario autenticado entre Lync Server y los servidores de AD FS, asigne un token con una extensión adecuada para abarcar la duración máxima de las reuniones de Lync. Por lo general, una duración de token de 240 minutos es suficiente.</p></li>
> </ul>


**Para configurar la autenticación multifactor**

1.  Instale un rol del servidor de federación de AD FS. Para más detalles, vea la Guía de implementación de Servicios de federación de Active Directory 2.0 en <http://go.microsoft.com/fwlink/p/?linkid=267511>.

2.  Cree certificados para AD FS. Para obtener más información, consulte la sección “Certificados de servidor de federación” del tema Planear e implementar AD FS para su uso con el inicio de sesión único, en [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Desde la interfaz de la línea de comandos de Windows PowerShell, ejecute el siguiente comando:
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Establezca una relación de usuario mediante la ejecución del siguiente comando:
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Defina las siguientes reglas de usuario de confianza:
    
```
$IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
```    
```
Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
```
```
Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
```

## Problemas conocidos que pueden impedir el inicio de sesión

## La fecha y la hora no son precisas en el dispositivo que ejecuta Aplicación de la Tienda Windows de Lync

La configuración de hora en el dispositivo debe estar sincronizada con la configuración de hora del servidor. Esto resulta particularmente importante en dispositivos que no están unidos a un dominio, como Microsoft Surface, y en otros dispositivos que ejecutan Windows RT. Para establecer la hora automáticamente en estos dispositivos desde un servidor horario, ejecute el comando siguiente en un símbolo del sistema con privilegios elevados en el dispositivo:

    w32tm /resync

## Aplicación de la Tienda Windows de Lync no puede acceder a los servicios o al servidor de Lync

Aplicación de la Tienda Windows de Lync posiblemente no tenga acceso a los servicios o al servidor de Lync a través de adaptadores de red, como módems USB 4G LTE, que no se registran con Windows 8 como dispositivos físicos. Aplicación de la Tienda Windows de Lync puede tener este problema aunque las aplicaciones y los exploradores de escritorio puedan acceder a otros servidores y sitios web.

## La aplicación de la Tienda Windows Lync no puede iniciar sesión con Lync Server 2010 ni con el servidor perimetral Office Communications Server 2007 R2

Si en la topología tiene Lync Server 2010 con el servidor perimetral Office Communications Server 2007 R2, deberá ejecutar la versión actualizada del Generador de topologías en la actualización acumulativa de julio de 2013 de Lync Server 2010. Las versiones anteriores del Generador de topologías no crean la asignación necesaria al servidor perimetral Office Communications Server 2007, por lo que los clientes de la aplicación de la Tienda Windows Lync no pueden iniciar sesión. Debe realizar los siguientes pasos:

1.  Instale la actualización acumulativa de julio de 2013 de Lync Server 2010 en los grupos de Lync Server 2010 y en los directores de Lync Server 2010.

2.  Para actualizar la configuración de la Detección automática de Lync para indicar que el punto de entrada SIP externo es la dirección del servidor perimetral, haga lo siguiente:
    
    1.  Abra Shell de administración de Lync Server.
    
    2.  Ejecute el siguiente comando:
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

## Lync Windows Store App no puede iniciar sesión debido a un error de validación del nombre del certificado

Puede ocurrir un problema de inicio de sesión para los usuarios de Office 365 no están ejecutando la versión más reciente de Aplicación de la Tienda Windows de Lync. En general, este problema ocurre al utilizar varios dominios (por ejemplo, cuando el URI de SIP es **userA@domainZ.com** y el servidor perimetral es **sip.domainX.com**). Para solucionar este problema, los usuarios deben instalar la versión más reciente de Aplicación de la Tienda Windows de Lync, para la cual es necesario tener Winows 8.1.

## Usar registros de Aplicación de la Tienda Windows de Lync para solucionar problemas

Puede usar los registros generados en el dispositivo para solucionar problemas. Los registros se almacenan en la siguiente carpeta:

%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing

Antes de obtener los registros de un usuario, asegúrese de que el registro esté activado y luego pídale que los guarde, para que toda la información almacenada en la memoria también se guarde en archivos del disco duro.

**Para activar el registro**

1.  Abra Aplicación de la Tienda Windows de Lync en el dispositivo.

2.  Deslice rápidamente desde el lado derecho de la pantalla. Si usa un mouse, apunte a la esquina superior derecha de la pantalla y mueva el puntero hacia abajo.

3.  Seleccione **Configuración**, elija **Opciones** y luego establezca **Registros de diagnóstico** en **Activado**.

4.  Si la opción **Registros de diagnóstico** ya estaba desactivada, debe reiniciar Lync. Para hacerlo, siga uno de estos pasos:
    
      - Reinicie el dispositivo.
    
      - Finalice la tarea de Lync y vuelva a iniciar la aplicación. Para finalizar la tarea, abra el Administrador de tareas de Windows, seleccione **Lync** y luego pulse **Finalizar tarea**. Si Lync no aparece en la lista, pulse **Más detalles** y busque Lync debajo de **Procesos en segundo plano**.

**Para guardar los registros**

1.  Abra Aplicación de la Tienda Windows de Lync en el dispositivo.

2.  Intente iniciar sesión.

3.  Deslice rápidamente desde el lado derecho de la pantalla. Si usa un mouse, apunte a la esquina superior derecha de la pantalla y mueva el puntero hacia abajo.

4.  Seleccione **Configuración**, **Acerca de** y, luego, **Guardar registros**.

