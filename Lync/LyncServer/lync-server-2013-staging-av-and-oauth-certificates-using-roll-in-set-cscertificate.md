---
title: "Prueba certif. OAuth y audio/vídeo en Lync Server 2013 con -Roll en Set-CsCertificate"
TOCTitle: "Prép. de cert. AV et OAuth dans LS 2013 grâce à -Roll dans app. comm. Set-CsCertificate"
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49888921
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prueba de certificados de OAuth y audio y vídeo en Lync Server 2013 utilizando -Roll en Set-CsCertificate

 

_**Última modificación del tema:** 2012-11-13_

Las comunicaciones de audio y vídeo (A/V) son un componente clave de Microsoft Lync Server 2013. Características como el uso compartido de aplicaciones y la conferencia de vídeo y audio dependen de los certificados asignados al Servicio perimetral A/V, específicamente al servicio de autenticación A/V.

> [!IMPORTANT]  
> <ol>
> <li><p>Esta nueva característica está diseñada para trabajar para el Servicio perimetral A/V y el certificado <em>OAuthTokenIssuer</em>. Otros tipos de certificado se pueden aprovisionar junto con el tipo de certificado OAuth y Servicio perimetral A/V, pero no se beneficiarán del mismo comportamiento de coexistencia que el certificado de Servicio perimetral A/V.</p></li>
> <li><p>Los cmdlets de PowerShell de Shell de administración de Lync Server usados para administrar Microsoft Lync Server 2013 hacen referencia al certificado de Servicio perimetral A/V como el tipo de certificado <em>AudioVideoAuthentication</em> y el certificado de OAuthServer como el tipo <em>OAuthTokenIssuer</em>. Para el resto de este tema y para identificar de manera única los certificados, se hará referencia a los mismos por el mismo tipo de identificador, <em>AudioVideoAuthentication</em> y <em>OAuthTokenIssuer</em>.</p></li>
> </ol>


El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V. Los tokens se generan desde atributos del certificado, y cuando el certificado expira, se producirá la pérdida de conexión y el requisito de volverse a unir con un nuevo token generado por el nuevo certificado. Una nueva característica de Lync Server 2013 aliviará este problema: la capacidad de organizar un nuevo certificado por adelantado del antiguo que expira y permitir que ambos certificados continúen funcionando durante un período de tiempo. Esta característica usa funcionalidad actualizada del cmdlet Set-CsCertificate de Shell de administración de Lync Server. El nuevo parámetro –Roll, con el parámetro existente –EffectiveDate, colocará el nuevo certificado AudioVideoAuthentication en el almacén de certificados. El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos. Comenzando por la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:

> [!TIP]  
> Mediante los cmdlets de Shell de administración de Lync Server para administrar certificados, puede solicitar certificados independientes y distintos para cada propósito en el Servidor perimetral. El uso del Asistente para certificados de la Asistente para la implementación de Lync Server le ayuda a crear certificados, pero normalmente es del tipo <strong>predeterminado</strong> que vincula todos los usos de certificado para el Servidor perimetral en un certificado único. La práctica recomendada si va a usar la característica de certificado en secuencia es desvincular el certificado AudioVideoAuthentication de los demás fines de certificado. Puede aprovisionar y organizar un certificado del tipo predeterminado pero solo la parte de AudioVideoAuthentication del certificado combinado se beneficiará del ensayo. Un usuario que participa en (por ejemplo) una conversación de mensajería instantánea cuando el certificado expira tendrá que cerrar sesión y volver a iniciar para usar el nuevo certificado asociado al Servidor perimetral de acceso. Se producirá un comportamiento similar para un usuario que participe en una conferencia web mediante el Servicio perimetral de conferencia web. El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores. Crea y administra el certificado en un lugar y el certificado se almacena en el Almacén de administración central para todos los demás servidores.



Se necesitan detalles adicionales para comprender por completo las opciones y los requisitos al usar el cmdlet Set-CsCertificate y al usarlo para realizar una copia intermedia de los certificados antes de la expiración del certificado actual. El parámetro –Roll es importante, pero, fundamentalmente, tiene un solo propósito. Si lo define como parámetro, está indicando a Set-CsCertificate que proporcionará información acerca del certificado que se verá afectado definido por –Type (por ejemplo, AudioVideoAuthentication y OAuthTokenIssuer), cuando el certificado se hará efectivo definido por –EffectiveDate.

**-Roll:** el parámetro –Roll es obligatorio y tiene dependencias que se deben suministrar con él. Parámetros obligatorios para definir por completo qué certificados se verán afectados y cómo se aplicarán:

**-EffectiveDate:** el parámetro –EffectiveDate define cuándo el nuevo certificado se hará coactivo con el certificado actual. El –EffectiveDate puede estar cercano al tiempo de expiración del certificado actual o bien, puede ser un período de tiempo mayor. Un –EffectiveDate mínimo recomendado para el certificado AudioVideoAuthentication sería de 8 horas, que es la vigencia de token predeterminada para los tokens de servicio perimetral AV emitidos con el certificado AudioVideoAuthentication.

Al organizar certificados OAuthTokenIssuer, hay diferentes requisitos para el plazo antes de que el certificado se haga efectivo. El tiempo mínimo que el certificado OAuthTokenIssuer debe tener para su plazo es de 24 horas antes del tiempo de expiración del certificado actual. El plazo extendido para la coexistencia es debido a otros roles de servidor que son independientes del certificado OAuthTokenIssuer (Exchange Server, por ejemplo) que tiene un tiempo de retención superior para los materiales clave de cifrado y autenticación creada de certificado.

**-Thumbprint:** la huella digital es un atributo del certificado que es único para dicho certificado. El parámetro –Thumbprint se usa para identificar el certificado que se verá afectado por las acciones del cmdlet Set-CsCertificate.

**-Type:** el parámetro –Type puede aceptar un tipo de uso de certificado único o una lista separada por comas de tipos de uso de certificado. Los tipos de certificados son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado. Por ejemplo, el tipo AudioVideoAuthentication es para que lo use el Servicio perimetral A/V y el servicio de autenticación AV. Si decide organizar y aprovisionar certificados de un tipo diferente al mismo tiempo, debe tener en cuenta el mayor plazo efectivo mínimo para los certificados. Por ejemplo, tiene que organizar certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer. Su –EffectiveDate mínima debe ser la mayor de los dos certificados, en este caso el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas. Si no desea organizar el certificado AudioVideoAuthentication con un plazo de 24 horas, organícelo por separado con una EffectiveDate que se adapte más a sus requisitos.

## Para actualizar o renovar un certificado de Servicio perimetral A/V con parámetros –Roll y -EffectiveDate

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Solicite una renovación o un nuevo certificado AudioVideoAuthentication con clave privada exportable para el certificado existente en el Servicio perimetral A/V.

3.  Importe el nuevo certificado AudioVideoAuthentication en el Servidor perimetral y todos los demás Servidor perimetral en su grupo de servidores (si tiene un grupo de servidores implementado).

4.  Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro –Roll con el parámetro –EffectiveDate. La fecha efectiva se debe definir como la hora de expiración del certificado actual (14:00:00 o 2:00:00 PM) menos la vigencia de token (de manera predeterminada, ocho horas). Esto nos proporciona una hora que el certificado debe establecerse en activo y es la –EffectiveDate \<string\>: “22/7/2012 6:00:00 AM”.
    
    > [!IMPORTANT]  
    > Para un Grupo de servidores perimetrales, debe tener todos los certificados de AudioVideoAuthentication implementados y aprovisionados por la fecha y la hora definidos por el parámetro –EffectiveDate del primer certificado implementado para evitar una posible interrupción de comunicaciones A/V debido a que el certificado más antiguo expira antes de que todos los tokens de cliente y consumidor se han renovado mediante el nuevo certificado.
    
    
    El comando Set-CsCertificate con el parámetro –Roll y –EffectiveTime:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Un comando Set-CsCertificate de ejemplo:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    > [!IMPORTANT]  
    > La EffectiveDate debe tener el formato que coincida con la configuración regional y de idioma de su servidor. El ejemplo usa la configuración regional y de idioma de Inglés (EE.UU.)
    


Para comprender mejor el proceso que Set-CsCertificate, -Roll y –EffectiveDate usan para organizar un nuevo certificado para emitir nuevos tokens AudioVideoAuthentication a la vez que usan un certificado existente para validar AudioVideoAuthentication que usan los consumidores, una escala de tiempo visual es un medio eficaz para comprender el proceso.

En el siguiente ejemplo, el administrador determina que el certificado Servicio perimetral A/V expirará a las 2:00:00 PM de día 22/07/2012. Solicita y recibe un nuevo certificado y lo importa a cada Servidor perimetral de este grupo de servidores. A las 2 AM del 22/07/2012, comienza a ejecutar Get-CsCertificate con –Roll, -Thumbprint igual a la cadena de huella digital del nuevo certificado y –EffectiveTime establecido en 22/07/2012 6:00:00 AM. Ejecuta este comando en cada Servidor perimetral.

![Usar los parámetros Roll y EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Usar los parámetros Roll y EffectiveDate.")

Cuando se alcanza la hora de vigencia (22/7/2012 6:00:00 AM), se emiten todos los nuevos tokens por el nuevo certificado. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el nuevo y recurrir al antiguo certificado continuará hasta la hora de expiración del antiguo certificado. Una vez que el antiguo certificado ha expirado (7/22/2012 2:00:00 PM), los tokens solo los validará el nuevo certificado. El antiguo certificado se puede quitar de manera segura mediante el cmdlet Remove-CsCertificate con el parámetro –Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

## Para actualizar o renovar un certificado OAuthTokenIssuer con parámetros –Roll y -EffectiveDate

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Solicite una renovación o un nuevo certificado OAuthTokenIssuer con clave privada exportable para el certificado existente en el Servicio perimetral A/V.

3.  Importe el nuevo certificado OAuthTokenIssuer para un Servidor front-end en su grupo de servidores (si tiene un grupo de servidores implementado). El certificado OAuthTokenIssuer se replica globalmente y solo se tiene que replicar y renovar en cualquier servidor de su implementación. El Servidor front-end se usa como ejemplo.

4.  Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro –Roll con el parámetro –EffectiveDate. La fecha de vigencia se debe definir como la hora de expiración de certificado actual (14:00:00 o 2:00:00 PM) menos un mínimo de 24 horas.
    
    El comando Set-CsCertificate con el parámetro –Roll y –EffectiveTime:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Un comando Set-CsCertificate de ejemplo:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    > [!IMPORTANT]  
    > La EffectiveDate debe tener el formato que coincida con la configuración regional y de idioma de su servidor. El ejemplo usa la configuración regional y de idioma de Inglés (EE.UU.)
    


Cuando se alcanza la hora efectiva (21.07.12 01:00:00 AM), todos los nuevos tokens se emiten por el nuevo certificado. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el nuevo y recurrir al antiguo certificado continuará hasta la hora de expiración del antiguo certificado. Una vez que el antiguo certificado ha expirado (22/7/2012 2:00:00 PM), los tokens solo los validará el nuevo certificado. El antiguo certificado se puede quitar de manera segura mediante el cmdlet Remove-CsCertificate con el parámetro –Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

## Vea también

#### Conceptos

[Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  

#### Otros recursos

[Configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  
[Remove-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCertificate)

