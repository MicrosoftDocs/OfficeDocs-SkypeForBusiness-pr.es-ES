---
title: Almacenamiento provisional de certificados de AV y OAuth con el rollo en Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4acdf759181dee3df872c7803ec595c63fb07016
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usar-Roll en Set-CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-13_

Las comunicaciones de audio/vídeo (A/V) son un componente clave de Microsoft Lync Server 2013. Características como el uso compartido de aplicaciones y las conferencias de audio y vídeo dependen de los certificados asignados al servicio perimetral de A/V, específicamente el servicio de autenticación A/V.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Esta nueva característica está diseñada para que funcione con el servicio a/V Edge y el certificado <EM>OAuthTokenIssuer</EM> . Se pueden aprovisionar otros tipos de certificados junto con el servicio perimetral A/V y el tipo de certificado OAuth, pero no se beneficiará del comportamiento de coexistencia del certificado de servicio perimetral A/V.</P>
> <LI>
> <P>Los cmdlets de PowerShell del shell de administración de Lync Server que se usan para administrar certificados de Microsoft Lync Server 2013 se refiere al certificado de servicio perimetral a/V como el tipo de certificado <EM>AudioVideoAuthentication</EM> y el certificado de OAuthServer como tipo <EM> OAuthTokenIssuer</EM>. Para el resto de este tema y para identificar de forma exclusiva los certificados, se les hará referencia mediante el mismo tipo de identificador, <EM>AudioVideoAuthentication</EM> y <EM>OAuthTokenIssuer</EM>.</P></LI></OL>



</div>

El servicio de autenticación A/V es responsable de emitir tokens que usan los clientes y otros consumidores de A/V. Los tokens se generan a partir de atributos del certificado y, cuando el certificado expira, se produce la pérdida de conexión y es necesario volver a unirse con un nuevo token generado por el nuevo certificado. Una nueva característica de Lync Server 2013 mejorará este problema: la capacidad de ensayar un nuevo certificado antes de que venza el antiguo y de permitir que ambos certificados sigan funcionando durante un período de tiempo. Esta característica usa la funcionalidad actualizada en el cmdlet del shell de administración Set-CsCertificate de Lync Server. El nuevo parámetro –Roll, con el parámetro existente –EffectiveDate, colocará el nuevo certificado AudioVideoAuthentication en el almacén de certificados. El certificado AudioVideoAuthentication más antiguo permanecerá todavía para validar con él los tokens emitidos. A partir de la implementación del nuevo certificado AudioVideoAuthentication, se producirá la siguiente serie de eventos:

<div>


> [!TIP]
> Usar los cmdlets del shell de administración de Lync Server para administrar certificados, puede solicitar certificados independientes y distintos para cada propósito en el servidor perimetral. Usar el Asistente para certificados en el Asistente para la implementación de Lync Server le ayuda a crear certificados, pero suele ser del tipo <STRONG>predeterminado</STRONG> que une todos los usos de certificados para el servidor perimetral en un solo certificado. La práctica recomendada si va a usar la característica de certificado rodante es desacoplar el certificado de AudioVideoAuthentication de los otros propósitos del certificado. Puede aprovisionar y ensayar un certificado del tipo predeterminado, pero solo la parte AudioVideoAuthentication del certificado combinado se beneficiará del almacenamiento provisional. Un usuario implicado en una conversación de mensajería instantánea, por ejemplo, en el momento en que expira el certificado, deberá cerrar sesión e iniciarla de nuevo para usar el nuevo certificado asociado con el servicio perimetral de acceso. Se producirá un comportamiento similar para un usuario implicado en una conferencia web con el servicio perimetral de conferencias web. El certificado OAuthTokenIssuer es un tipo específico que se comparte en todos los servidores. Cree y administre el certificado en un solo lugar y el certificado se almacena en el almacén de administración central para todos los demás servidores.



</div>

Es necesario más detalles para comprender completamente sus opciones y requisitos al usar el cmdlet Set-CsCertificate y su uso para organizar certificados antes de que expire el certificado actual. El parámetro – roll es importante, pero esencialmente un único fin. Si lo define como un parámetro, está indicando a set-CsCertificate que le proporcionará información sobre el certificado que se verá afectado por tipo (por ejemplo, AudioVideoAuthentication y OAuthTokenIssuer), cuando el certificado se convierta en efectivo definido por – EffectiveDate.

**-Roll:** El parámetro – roll es obligatorio y tiene dependencias que deben proporcionarse con él. Parámetros obligatorios para definir completamente Qué certificados se verán afectados y cómo se aplicarán:

**-EffectiveDate:** El parámetro-EffectiveDate define cuándo el nuevo certificado volverá a estar activo con el certificado actual. El – EffectiveDate puede estar cerca de la hora de expiración del certificado actual o puede ser un período de tiempo más largo. Un mínimo recomendado: EffectiveDate para el certificado de AudioVideoAuthentication sería de 8 horas, que es el token de vigencia predeterminado para los tokens del servicio de borde AV emitido con el certificado de AudioVideoAuthentication.

Al ensayar certificados de OAuthTokenIssuer, existen diferentes requisitos para el tiempo de adelanto antes de que el certificado pueda ser efectivo. El tiempo mínimo que el certificado de OAuthTokenIssuer debería tener por su tiempo de adelanto es de 24 horas antes de la fecha de expiración del certificado actual. El tiempo de adelanto ampliado de la coexistencia se debe a que existen otros roles de servidor que dependen del certificado OAuthTokenIssuer (Exchange Server, por ejemplo), lo que tiene un mayor tiempo de retención para la autenticación y la clave de cifrado del certificado cosecha.

**-Huella digital:** La huella digital es un atributo en el certificado que es exclusivo de ese certificado. El parámetro – Thumbprint se usa para identificar el certificado que se verá afectado por las acciones del cmdlet Set-CsCertificate.

**-Escriba:** El parámetro – type puede aceptar un único tipo de uso de certificado o una lista separada por comas de tipos de uso de certificados. Los tipos de certificado son aquellos que identifican al cmdlet y al servidor cuál es el propósito del certificado. Por ejemplo, escriba AudioVideoAuthentication es para que lo use el servicio A/V Edge y el servicio de autenticación de AV. Si decide organizar y aprovisionar certificados de un tipo diferente al mismo tiempo, debe tener en cuenta el tiempo de adelanto mínimo mínimo requerido para los certificados. Por ejemplo, necesita organizar los certificados de tipo AudioVideoAuthentication y OAuthTokenIssuer. El mínimo: EffectiveDate debe ser el mayor de los dos certificados, en este caso el OAuthTokenIssuer, que tiene un plazo mínimo de 24 horas. Si no desea ensayar el certificado de AudioVideoAuthentication con un tiempo de adelanto de 24 horas, hágalo por separado con un EffectiveDate que sea más conveniente para sus requisitos.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado de servicio perimetral a/V con parámetros-roll y-EffectiveDate

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Solicite una renovación o un certificado de AudioVideoAuthentication nuevo con una clave privada exportable para el certificado existente en el servicio perimetral A/V.

3.  Importe el nuevo certificado AudioVideoAuthentication al servidor perimetral y a todos los demás servidores perimetrales de su grupo (si tiene un grupo implementado).

4.  Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro-roll con el parámetro – EffectiveDate. La fecha de vigencia debe definirse como la hora de caducidad del certificado actual (14:00:00 o 2:00:00 P.M.) menos vigencia del token (de forma predeterminada ocho horas). Esto nos da la ocasión de que el certificado deba establecerse en activo y es la cadena \<\>– EFFECTIVEDATE: "7/22/2012 6:00:00 a.m.".
    
    <div>
    

    > [!IMPORTANT]
    > En el caso de un grupo perimetral, debe tener todos los certificados de AudioVideoAuthentication implementados y aprovisionados por la fecha y la hora definida por el parámetro – EffectiveDate del primer certificado implementado para evitar posibles interrupciones en las comunicaciones a/V debido al antiguo el certificado vence antes de que todos los tokens de cliente y cliente se hayan renovado con el nuevo certificado.

    
    </div>
    
    El comando set-CsCertificate con el parámetro-roll y-EffectiveTime:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Un ejemplo del comando set-CsCertificate:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > El EffectiveDate debe tener el formato para que coincida con la configuración regional y de idioma del servidor. El ejemplo usa la región de inglés norteamericano y la configuración de idioma

    
    </div>

Para obtener más información sobre el proceso que establece-CsCertificate,-roll y – EffectiveDate usar para ensayar un nuevo certificado para emitir nuevos tokens de AudioVideoAuthentication mientras se sigue usando un certificado existente para validar AudioVideoAuthentication que se están usando por los consumidores, una escala de tiempo visual es un medio eficaz para comprender el proceso.

En el siguiente ejemplo, el administrador determina que el certificado de servicio perimetral A/V debe expirar a los 2:00:00 PM en 07/22/2012. Solicita y recibe un nuevo certificado y lo importa a cada servidor perimetral de su grupo. A la 2 de la 07/22/2012, comienza a ejecutar Get-CsCertificate con – roll,-Thumbprint es igual a la cadena de la huella digital del nuevo certificado, y-EffectiveTime se establece en 07/22/2012 6:00:00 AM. Este comando se ejecuta en cada servidor perimetral.

![Usar los parámetros roll y EffectiveDate.] (images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Usar los parámetros roll y EffectiveDate.")

Cuando se alcance el tiempo de vigencia (7/22/2012 6:00:00 A.M.), el nuevo certificado emitirá todos los tokens nuevos. Cuando se validan los tokens, los tokens se validan en primer lugar con el nuevo certificado. Si se produce un error en la validación, se intenta el certificado anterior. El proceso de prueba del nuevo y del certificado anterior continuará hasta la fecha de vencimiento del certificado anterior. Una vez que el certificado antiguo haya expirado (7/22/2012 2:00:00 PM), los tokens solo se validarán con el nuevo certificado. El certificado antiguo se puede eliminar de forma segura con el cmdlet Remove-CsCertificate con el parámetro-Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>Para actualizar o renovar un certificado de OAuthTokenIssuer con parámetros-roll y-EffectiveDate

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Solicite una renovación o un certificado de OAuthTokenIssuer nuevo con una clave privada exportable para el certificado existente en el servicio perimetral A/V.

3.  Importe el nuevo certificado OAuthTokenIssuer a un servidor front-end de su grupo (si tiene un grupo implementado). El certificado OAuthTokenIssuer se replica de forma global y solo es necesario actualizarlo y renovarlo en cualquier servidor de la implementación. El servidor front-end se usa como ejemplo.

4.  Configure el certificado importado con el cmdlet Set-CsCertificate y use el parámetro-roll con el parámetro – EffectiveDate. La fecha de vigencia debe definirse como la hora de caducidad del certificado actual (14:00:00 o 2:00:00 P.M.) menos un mínimo de 24 horas.
    
    El comando set-CsCertificate con el parámetro-roll y-EffectiveTime:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Un ejemplo del comando set-CsCertificate:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > El EffectiveDate debe tener el formato para que coincida con la configuración regional y de idioma del servidor. El ejemplo usa la región de inglés norteamericano y la configuración de idioma

    
    </div>

Cuando se alcance el tiempo de vigencia (7/21/2012 1:00:00 A.M.), el nuevo certificado emitirá todos los tokens nuevos. Cuando se validan los tokens, los tokens se validan en primer lugar con el nuevo certificado. Si se produce un error en la validación, se intenta el certificado anterior. El proceso de prueba del nuevo y del certificado anterior continuará hasta la fecha de vencimiento del certificado anterior. Una vez que el certificado antiguo haya expirado (7/22/2012 2:00:00 PM), los tokens solo se validarán con el nuevo certificado. El certificado antiguo se puede eliminar de forma segura con el cmdlet Remove-CsCertificate con el parámetro-Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Vea también


[Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

