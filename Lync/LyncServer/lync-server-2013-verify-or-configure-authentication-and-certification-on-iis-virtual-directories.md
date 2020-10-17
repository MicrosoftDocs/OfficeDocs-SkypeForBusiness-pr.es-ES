---
title: 'Lync Server 2013: comprobar o configurar la autenticación y la certificación en los directorios virtuales de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c07fc83680fd6b1d3f4d0d24429165ff9cc5ca65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518617"
---
# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Comprobar o configurar la autenticación y la certificación en directorios virtuales de IIS en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-25_

Use el siguiente procedimiento para configurar el certificado en los directorios virtuales de Internet Information Services (IIS) o comprobar que el certificado está configurado correctamente. Realice el procedimiento siguiente en cada servidor que ejecute IIS en el grupo de servidores interno de Lync Server y en el director opcional o en los servidores de grupos de directores.

<div>


> [!NOTE]  
> El siguiente procedimiento define un procedimiento para solicitar un certificado combinado que se usa para todos los propósitos Lync Server, sitio Web interno y sitio web externo de IIS. Lync Server 2010 incorporó un conjunto de cmdlets de Windows PowerShell de Shell de administración de Lync Server &nbsp; para el propósito expreso de administrar la solicitud de certificados, la importación y la asignación. Este procedimiento supone que existe una entidad de certificación (CA) implementada internamente que puede procesar la solicitud. Si usa certificados públicos para los propósitos de Lync Server o la CA requiere una solicitud sin conexión, consulte la sintaxis detallada de este tema para obtener información sobre el parámetro – output. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Solicitud-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Configuración de la autenticación y los certificados en los directorios virtuales IIS

1.  Para completar correctamente lo siguiente, debe iniciar sesión en el equipo (servidor front-end o director) donde están instalados los servicios web y ser un administrador local. Debe tener permisos de **lectura** e **inscripción** en la entidad de certificación a la que solicitará los certificados, si la entidad de certificación es la entidad de certificación de su organización. No necesitará permisos de la entidad de certificación si configura y envía una solicitud de certificado fuera de línea.

2.  Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas** y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.

3.  En **Administrador de Internet Information Services (IIS)**, seleccione **ServerName**. En **Vista Características**, seleccione **Certificados de servidor**, haga clic con el botón secundario y seleccione **Abrir característica**.
    
    <div>
    

    > [!TIP]  
    > En la Vista Características de certificados de servidor, si hay certificados asignados al servidor, aparecerán aquí. Si hay un certificado que coincide con los requisitos del sitio web externo en IIS, puede volver a utilizar este certificado. Para ver un certificado, haga clic con el botón secundario en el certificado y seleccione <STRONG>Ver…</STRONG>

    
    </div>

4.  En el servidor front-end o director para el que va a solicitar el certificado, haga clic en **Inicio**, seleccione **todos los programas**, seleccione **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

5.  En el shell de administración de Lync Server, escriba lo siguiente:
    
        Get-CsCertificate
    
    El resultado es una lista de los certificados que están actualmente en el servidor del almacén de certificados personales del equipo. Ten en cuenta que en el certificado combinado (es decir, donde los servicios web internos y los servicios web externos predeterminados están utilizando el mismo certificado), verá que la propiedad de uso se rellenará con predeterminado, WebServicesInternal y WebServicesExternal. Además, la propiedad huella digital será la misma para cada uno de los tipos de uso. En este ejemplo se muestra un resultado de ejemplo de Get-CsCertificate:
    
    ![Get-CsCertificate información sobre el estado de scert actual](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate información sobre el estado scert actual")

6.  En el shell de administración de Lync Server, escriba lo siguiente:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Donde el comando completo aparecería como en el siguiente ejemplo:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > De modo predeterminado, Request-CsCertificate rellenará el nombre de asunto con el nombre del servidor o del grupo de servidores y rellenará las entradas en el nombre alternativo del asunto con el servidor FQDN, el grupo de servidores FQDN, los FQDN de URL simples y los FQDN de los servicios web internos y externos. Esto lo hace haciendo referencia al documento de topología de su implementación. Si falta un valor y ha especificado el parámetro –Verbose, se le notificará que los valores calculados y reales de los nombres alternativos son diferentes, pero no se le informará de los valores que faltan. Se le proporcionará el valor calculado completo al que hace referencia el cmdlet. Utilice la cadena de nombres alternativos calculados en el resultado para volver a solicitar un nuevo certificado que incluya todos los valores

    
    </div>
    
    ![Resultado de la solicitud del certificado mediante request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Resultado de la solicitud del certificado mediante Request-CsCertifica")

7.  En el shell de administración de Lync Server, escriba lo siguiente:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Donde el comando completo aparecería como en el siguiente ejemplo:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    para>El resultado del cmdlet Set-CsCertificate mostrará que se ha asignado el mismo certificado (identificado por la huella digital del certificado) para el uso predeterminado, WebServicesExternal y WebServicesInternal u
    
    ![Resultado de Set-CsCertificate en IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Resultado de Set-CsCertificate en IIS WebExt")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Para comprobar o configurar la autenticación y la certificación en directorios virtuales de IIS

1.  Haga clic en **Inicio**, elija **Todos los programas**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.

2.  En el **Administrador de Internet Information Services (IIS)**, expanda **ServerName**y, a continuación, expanda **sitios**.

3.  Haga clic con el botón secundario en **Sitio web externo de Lync Server** y, a continuación, haga clic en **Modificar enlaces**

4.  Compruebe que https está asociado al puerto 4443 y haga clic en **https**.

5.  Seleccione la entrada HTTPS, haga clic en **Editar**y, a continuación, compruebe que Lync Server WebServicesExternalCertificate está enlazado a este protocolo. Compare la huella digital del cmdlet Set-CsCertificate para asegurar que el certificado esperado está correctamente asociado con el enlace HTTPS.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

