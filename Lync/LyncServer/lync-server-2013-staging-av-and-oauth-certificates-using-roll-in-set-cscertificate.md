---
title: Almacenamiento provisional de certificados AV y OAuth usando-Roll en Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f59cba907a57d4646a469daa72bae1355f09a662
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-13_

Las comunicaciones de audio y vídeo (A/V) son un componente clave de Microsoft Lync Server 2013. Características como el uso compartido de aplicaciones y las conferencias de audio y vídeo se basan en los certificados asignados al servicio perimetral a/V, específicamente en el servicio de autenticación A/V.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Esta nueva característica está diseñada para funcionar para el servicio perimetral A/V y el certificado <EM>OAuthTokenIssuer</EM> . Se pueden aprovisionar otros tipos de certificados junto con el servicio perimetral A/V y el tipo de certificado OAuth, pero no se beneficiarán del comportamiento de coexistencia que tendrá el certificado del servicio perimetral A/V.</P>
> <LI>
> <P>Los cmdlets de PowerShell del shell de administración de Lync Server que se usan para administrar certificados de Microsoft Lync Server 2013 hacen referencia al certificado del servicio perimetral A/V como el tipo de certificado <EM>AudioVideoAuthentication</EM> y el certificado OAuthServer como tipo <EM>OAuthTokenIssuer</EM>. Para el resto de este tema y para identificar de forma exclusiva los certificados, se hará referencia a ellos por el mismo tipo de identificador, <EM>AudioVideoAuthentication</EM> y <EM>OAuthTokenIssuer</EM>.</P></LI></OL>



</div>

El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V. Los tokens se generan desde atributos del certificado, y cuando el certificado expira, se producirá la pérdida de conexión y el requisito de volverse a unir con un nuevo token generado por el nuevo certificado. Una nueva característica de Lync Server 2013 solucionará este problema: la capacidad de ensayar un nuevo certificado antes de la antigua expiración y permitir que ambos certificados sigan funcionando durante un período de tiempo. Esta característica usa la funcionalidad actualizada en el cmdlet Set-CsCertificate Lync Server Management Shell. El nuevo parámetro –Roll, con el parámetro existente –EffectiveDate, colocará el nuevo certificado AudioVideoAuthentication en el almacén de certificados. El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos. Comenzando por la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:

<div>


> [!TIP]
> Con los cmdlets del shell de administración de Lync Server para administrar certificados, puede solicitar certificados independientes y distintos para cada propósito en el servidor perimetral. El uso del Asistente para certificados en el Asistente para la implementación de Lync Server le ayudará a crear certificados, pero suele ser el tipo <STRONG>predeterminado</STRONG> que une todos los usos de certificados para el servidor perimetral en un único certificado. La práctica recomendada si va a usar la característica de certificado en secuencia es desvincular el certificado AudioVideoAuthentication de los demás fines de certificado. Puede aprovisionar y organizar un certificado del tipo predeterminado pero solo la parte de AudioVideoAuthentication del certificado combinado se beneficiará del ensayo. Un usuario implicado en una conversación de mensajería instantánea (por ejemplo) cuando expire el certificado tendrá que cerrar la sesión y volver a iniciarla para usar el nuevo certificado asociado al servicio perimetral de acceso. Se producirá un comportamiento similar para un usuario implicado en una conferencia Web mediante el servicio perimetral de conferencia Web. El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores. El certificado se crea y se administra en un solo punto y el certificado se almacena en el almacén de administración central para todos los demás servidores.



</div>

Se necesitan detalles adicionales para comprender por completo sus opciones y requisitos al usar el cmdlet Set-CsCertificate y al usarlo para organizar certificados anteriores al certificado actual que expira. El parámetro –Roll es importante pero esencialmente de un solo propósito. Si lo define como un parámetro, estará indicando a set-CsCertificate que proporcionará información sobre el certificado que se verá afectada por el tipo (por ejemplo, AudioVideoAuthentication y OAuthTokenIssuer), cuando el certificado se convertirá en efectivo definido por – EffectiveDate.

**-Roll:** El parámetro – roll es obligatorio y tiene dependencias que se deben proporcionar junto con él. Parámetros obligatorios para definir por completo qué certificados se verán afectados y cómo se aplicarán:

**-EffectiveDate:** El parámetro – EffectiveDate define cuándo el nuevo certificado se convertirá en coactivo con el certificado actual. El –EffectiveDate puede estar cercano al tiempo de expiración del certificado actual o bien, puede ser un período de tiempo mayor. Un –EffectiveDate mínimo recomendado para el certificado AudioVideoAuthentication sería de 8 horas, que es la vigencia de token predeterminada para los tokens de servicio perimetral AV emitidos con el certificado AudioVideoAuthentication.

Al organizar certificados OAuthTokenIssuer, hay diferentes requisitos para el plazo antes de que el certificado se haga efectivo. El tiempo mínimo que el certificado OAuthTokenIssuer debe tener para su plazo es de 24 horas antes del tiempo de expiración del certificado actual. El plazo extendido para la coexistencia es debido a otros roles de servidor que son independientes del certificado OAuthTokenIssuer (Exchange Server, por ejemplo) que tiene un tiempo de retención superior para los materiales clave de cifrado y autenticación creada de certificado.

**-Thumbprint:** La huella digital es un atributo en el certificado que es único para ese certificado. El parámetro –Thumbprint se usa para identificar el certificado que se verá afectado por las acciones del cmdlet Set-CsCertificate.

**-Tipo:** El parámetro – type puede aceptar un solo tipo de uso de certificado o una lista separada por comas de tipos de uso de certificado. Los tipos de certificado son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado. Por ejemplo, escriba AudioVideoAuthentication es para que lo use el servicio perimetral A/V y el servicio de autenticación AV. Si decide organizar y aprovisionar certificados de un tipo diferente al mismo tiempo, debe tener en cuenta el plazo de entrega efectivo mínimo que se necesita para los certificados. Por ejemplo, necesita organizar los certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer. El valor mínimo de EffectiveDate debe ser el mayor de los dos certificados, en este caso el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas. Si no desea ensayar el certificado AudioVideoAuthentication con un tiempo de entrega de 24 horas, guárdelo por separado con un EffectiveDate que sea más importante para sus requisitos.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado de servicio perimetral a/V con parámetros – roll y-EffectiveDate

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Solicite una renovación o un nuevo certificado AudioVideoAuthentication con clave privada exportable para el certificado existente en el servicio perimetral A/V.

3.  Importe el nuevo certificado AudioVideoAuthentication en el servidor perimetral y en el resto de servidores perimetrales del grupo de servidores (si tiene un grupo de servidores implementado).

4.  Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro –Roll con el parámetro –EffectiveDate. La fecha efectiva se debe definir como la hora de expiración del certificado actual (14:00:00 o 2:00:00 PM) menos la vigencia de token (de manera predeterminada, ocho horas). Esto nos da el tiempo necesario para establecer el certificado en activo y es la cadena \<\>– EFFECTIVEDATE: "7/22/2012 6:00:00 a.m.".
    
    <div>
    

    > [!IMPORTANT]
    > Para un grupo de servidores perimetrales, debe tener todos los certificados AudioVideoAuthentication implementados y aprovisionados por la fecha y hora definida por el parámetro – EffectiveDate del primer certificado implementado para evitar posibles interrupciones de comunicaciones a/V debido a que el certificado anterior expira antes de que todos los tokens de cliente y consumidor se hayan renovado con el nuevo certificado.

    
    </div>
    
    El comando Set-CsCertificate con el parámetro –Roll y –EffectiveTime:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Un comando Set-CsCertificate de ejemplo:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > La EffectiveDate debe tener el formato que coincida con la configuración regional y de idioma de su servidor. El ejemplo usa la configuración regional y de idioma de Inglés (EE.UU.)

    
    </div>

Para comprender mejor el proceso que Set-CsCertificate, -Roll y –EffectiveDate usan para organizar un nuevo certificado para emitir nuevos tokens AudioVideoAuthentication a la vez que usan un certificado existente para validar udioVideoAuthentication que usan los consumidores, una escala de tiempo visual es un medio eficaz para comprender el proceso.

En el siguiente ejemplo, el administrador determina que el certificado del servicio perimetral A/V debe expirar a las 2:00:00 PM en 07/22/2012. Solicita y recibe un nuevo certificado y lo importa a cada servidor perimetral en su grupo de servidores. A las  2 AM del 22/07/2012, comienza a ejecutar Get-CsCertificate con –Roll, -Thumbprint igual a la cadena de huella digital del nuevo certificado y –EffectiveTime establecido en 22/07/2012 6:00:00 AM. Ejecuta este comando en cada servidor perimetral.

![Con los parámetros roll y EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Con los parámetros roll y EffectiveDate.")

Cuando se alcanza la hora de vigencia (22/7/2012 6:00:00 AM), se emiten todos los nuevos tokens por el nuevo certificado. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el nuevo y recurrir al antiguo certificado continuará hasta la hora de expiración del antiguo certificado. Una vez que el antiguo certificado ha expirado (7/22/2012 2:00:00 PM), los tokens solo los validará el nuevo certificado. El antiguo certificado se puede quitar de manera segura mediante el cmdlet Remove-CsCertificate con el parámetro –Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado OAuthTokenIssuer con parámetros –Roll y -EffectiveDate

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Solicite una renovación o un nuevo certificado OAuthTokenIssuer con clave privada exportable para el certificado existente en el servicio perimetral A/V.

3.  Importe el nuevo certificado OAuthTokenIssuer en un servidor front-end del grupo de servidores (si tiene un grupo de servidores implementado). El certificado OAuthTokenIssuer se replica globalmente y solo se tiene que replicar y renovar en cualquier servidor de su implementación. El servidor front-end se usa como ejemplo.

4.  Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro –Roll con el parámetro –EffectiveDate. La fecha de vigencia se debe definir como la hora de expiración de certificado actual (14:00:00 o 2:00:00 PM) menos un mínimo de 24 horas.
    
    El comando Set-CsCertificate con el parámetro –Roll y –EffectiveTime:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Un comando Set-CsCertificate de ejemplo:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > La EffectiveDate debe tener el formato que coincida con la configuración regional y de idioma de su servidor. El ejemplo usa la configuración regional y de idioma de Inglés (EE.UU.)

    
    </div>

Cuando se alcanza la hora efectiva (21.07.12 01:00:00 AM), todos los nuevos tokens se emiten por el nuevo certificado. Cuando se validan los tokens, estos se validarán primero con el nuevo certificado. Si se produce un error en la validación, se prueba el antiguo certificado. El proceso de probar el nuevo y recurrir al antiguo certificado continuará hasta la hora de expiración del antiguo certificado. Una vez que el antiguo certificado ha expirado (22/7/2012 2:00:00 PM), los tokens solo los validará el nuevo certificado. El antiguo certificado se puede quitar de manera segura mediante el cmdlet Remove-CsCertificate con el parámetro –Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación de certificados de servidor perimetral en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

