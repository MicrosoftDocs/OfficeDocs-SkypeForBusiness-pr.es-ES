---
title: 'Lync Server 2013: Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-25_

Use el procedimiento siguiente para configurar el certificado en los directorios virtuales de servicios de Internet Information Server (IIS) o comprobar que el certificado está configurado correctamente. Realice el siguiente procedimiento en cada servidor que ejecute IIS en el grupo de servidores de Lync interno y en el director opcional. o servidores de grupo de directores.

<div>


> [!NOTE]  
> El procedimiento siguiente define un procedimiento para solicitar un certificado combinado que se usa para todos los propósitos de Lync Server, sitio Web interno y sitio web externo en IIS. Lync Server 2010 presentó un conjunto de cmdlets de Windows&nbsp;PowerShell de Shell de administración de Lync Server para la administración de solicitudes de certificados, importaciones y asignaciones. En el procedimiento se supone que hay una entidad de certificación (CA) implementada internamente que puede procesar la solicitud. Si usa certificados públicos para sus propósitos de Lync Server, o si su CA requiere una solicitud sin conexión, consulte la sintaxis detallada de este tema para obtener información sobre el parámetro-output. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Solicitud-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Para configurar la autenticación y los certificados en directorios virtuales de IIS

1.  Para completar correctamente lo siguiente, debe haber iniciado sesión en el equipo (servidor front-end o director) donde están instalados los servicios web y ser administradores locales. Debe tener permisos de **lectura** e **inscripción** en la entidad de certificación de la que va a solicitar certificados, si la entidad emisora de certificados es la entidad de certificación de su organización. No necesita permisos para la entidad emisora de certificados si va a configurar y enviar una solicitud de certificado sin conexión.

2.  Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.

3.  En el **Administrador de Internet Information Services (IIS)**, seleccione **ServerName**. En la **vista características**, seleccione **certificados de servidor**, haga clic con el botón derecho y seleccione **abrir característica**.
    
    <div>
    

    > [!TIP]  
    > En la vista características de certificados de servidor, si hay certificados asignados al servidor, aparecerán aquí. Si hay un certificado que cumpla los requisitos para el sitio web externo en IIS, puede volver a usarlo. Para ver un certificado, haga clic con el botón derecho en el certificado y seleccione <STRONG>ver...</STRONG>

    
    </div>

4.  En el servidor front-end o director para el que va a solicitar el certificado, haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

5.  En el shell de administración de Lync Server, escriba lo siguiente:
    
        Get-CsCertificate
    
    El resultado es una lista de los certificados que se encuentran actualmente en el servidor del almacén de certificados personal del equipo. Tenga en cuenta que en el certificado combinado (es decir, cuando el valor predeterminado, servicios Web internos y servicios web externos estén usando el mismo certificado) verá que la propiedad use se rellenará con default, WebServicesInternal y WebServicesExternal. Además, la propiedad Thumbprint será la misma para cada uno de los tipos de uso. En este ejemplo se muestra un ejemplo de la salida de Get-CsCertificate:
    
    ![Get-CsCertificate información sobre el estado actual de scert] (images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate información sobre el estado actual de scert")

6.  En el shell de administración de Lync Server, escriba lo siguiente:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Donde el comando completo tendría el siguiente ejemplo:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > De forma predeterminada, Request-CsCertificate rellenará el nombre del asunto con el nombre del servidor o grupo de servidores y llenará las entradas en el nombre de asunto alternativo con el servidor FQDN, FQDN del grupo, FQDN de dirección URL simple y FQDN de los servicios Web internos y externos. Para ello, hace referencia al documento de topología de su implementación. Si falta un valor y ha especificado el parámetro – verbose, se le notificará que los valores calculados y reales de los nombres alternativos son diferentes, pero no le informan los valores que faltan. Le proporciona el valor calculado completo al que hace referencia el cmdlet. Use la cadena de nombres alternativos calculados en la salida para volver a solicitar un nuevo certificado que incluirá todos los valores.

    
    </div>
    
    ![Resultado de la solicitud del certificado mediante la solicitud-CsCertifica] (images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Resultado de la solicitud del certificado mediante la solicitud-CsCertifica")

7.  En el shell de administración de Lync Server, escriba lo siguiente:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Donde el comando completo tendría el siguiente ejemplo:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    El resultado del cmdlet Set-CsCertificate mostrará que el mismo certificado (identificado por la huella digital del certificado) se asigna al uso predeterminado, WebServicesExternal y WebServicesInternal.
    
    ![Resultado de set-CsCertificate en IIS webext] (images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Resultado de set-CsCertificate en IIS webext")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Para comprobar o configurar la autenticación y los certificados en los directorios virtuales de IIS

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.

2.  En el **Administrador de Internet Information Services (IIS)**, expanda **ServerName**y, a continuación, expanda **sites**.

3.  Haga clic con el botón secundario en **sitio web externo de Lync Server**y, a continuación, haga clic en **Editar enlaces**

4.  Compruebe que https está asociado con el puerto 4443 y, a continuación, haga clic en **https**.

5.  Seleccione la entrada HTTPS, haga clic en **Editar**y, a continuación, compruebe que Lync Server WebServicesExternalCertificate está enlazado a este protocolo. Compare la huella digital del cmdlet Set-CsCertificate para asegurarse de que el certificado esperado esté correctamente asociado con el enlace HTTPS.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

