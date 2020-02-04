---
title: 'Lync Server 2013: configuración de certificados para la detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1f2a89cf317a0ea5bead4bb24eba1469ef1108e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Configuración de certificados para la detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-12_

Los certificados para el grupo de directores, el grupo front-end y el proxy inverso requieren entradas de nombre alternativo adicionales para admitir conexiones seguras con clientes de Lync.

<div>


> [!NOTE]  
> Puede usar el cmdlet <STRONG>Get-CsCertificate</STRONG> para ver información sobre los certificados asignados actualmente. Sin embargo, la vista predeterminada trunca las propiedades del certificado y no muestra todos los valores de la propiedad SubjectAlternativeNames. Puede usar los cmdlets <STRONG>Get-CsCertificate</STRONG> , <STRONG>request-</STRONG>CsCertificate y <STRONG>set-CsCertificate</STRONG> para ver cierta información y para solicitar y asignar certificados. Sin embargo, no es el mejor método de uso si no está seguro de las propiedades de los nombres alternativos de asunto (SAN) en el certificado actual. Para ver el certificado y todos los miembros de la propiedad, se recomienda usar el complemento certificados en <EM>Microsoft Management Console (MMC)</EM> o usar el Asistente para la implementación de Lync Server. En el Asistente para la implementación de Lync Server, puede usar el Asistente para la implementación de certificados para ver las propiedades del certificado. Los procedimientos para ver, solicitar y asignar un certificado mediante el shell de administración de Lync Server y <EM>Microsoft Management Console (MMC)</EM> se detallan en los procedimientos siguientes. Para usar el Asistente para la implementación de Lync Server, vea detalles aquí si ha implementado el grupo opcional de directores o directores: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurar certificados para el Director en Lync Server 2013</A>. Para el servidor front-end o el grupo front-end, consulte los detalles aquí: <A href="lync-server-2013-configure-certificates-for-servers.md">configurar certificados para servidores en Lync Server 2013</A>.<BR>Los pasos iniciales de este procedimiento son pasos de preparación para orientarse en cuanto a la función de reproducción de los certificados actuales. De forma predeterminada, los certificados no tendrán un lyncdiscover. &lt;sipdomain&gt; o lyncdiscoverinternal. &lt;nombre&gt; de dominio interno, a menos que haya instalado previamente servicios de movilidad o haya preparado los certificados con antelación. Este procedimiento usa el ejemplo de nombre de dominio SIP ' contoso.com ' y el nombre de dominio interno ' contoso.net ' de ejemplo.<BR>La configuración de certificado predeterminada para Lync Server 2013 y Lync Server 2010 es usar un único certificado (denominado ' predeterminado ') con los propósitos predeterminados (para todos los propósitos excepto los servicios web), WebServicesExternal y WebServicesInternal. Una configuración opcional es usar certificados independientes para cada propósito. Los certificados se pueden administrar mediante el shell de administración de Lync Server y los cmdlets de Windows PowerShell, o bien mediante el Asistente para certificados del Asistente para la implementación de Lync Server.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Para actualizar certificados con nombres alternativos de asunto nuevos mediante el shell de administración de Lync Server

1.  Inicie sesión en el equipo con una cuenta que tenga derechos y permisos de administrador local.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Averigüe qué certificados se han asignado al servidor y para qué tipo de uso. Necesitas esta información en el siguiente paso para asignar el certificado actualizado. En la línea de comandos, escriba:
    
        Get-CsCertificate

4.  Mire la salida del paso anterior para ver si se asigna un único certificado para varios usos o si se asigna un certificado diferente para cada uso. Busque el parámetro use para saber cómo se usa un certificado. Compare el parámetro de la huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos.

5.  Actualice el certificado. En la línea de comandos, escriba:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por ejemplo, si el cmdlet **Get-CsCertificate** muestra un certificado con el uso predeterminado, otro con el uso de WebServicesInternal y otro con el uso de WebServicesExternal, y todos tenían el mismo valor de huella digital, en la línea de comandos, escriba:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Si se asigna un certificado independiente para cada uso (el valor de la huella digital es diferente para cada certificado), es importante que no ejecute el cmdlet **set-CsCertificate** con varios tipos. En este caso, ejecute el cmdlet **set-CsCertificate** por separado para cada uso. Por ejemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para ver el certificado, haga clic en **Inicio**, haga clic en **Ejecutar...**. Escriba MMC para abrir la consola de administración de Microsoft.

7.  En el menú MMC, seleccione **archivo**, seleccione **Agregar o quitar complemento...**, seleccione certificados. Haga clic en **Agregar**. Cuando se le solicite, seleccione **cuenta de equipo**y, a continuación, haga clic en **siguiente**.

8.  Si el certificado se encuentra en este equipo, seleccione **equipo local**. Si el certificado se encuentra en otro equipo, seleccione **otro equipo**, escriba el nombre de dominio completo del equipo o haga clic en **examinar** en **Escriba el nombre de objeto para seleccionar**, escriba el nombre del equipo. Haga clic en **Comprobar nombres**. Cuando el nombre del equipo se resuelva, estará subrayado. Haga clic en **Aceptar**y, después, en **Finalizar**. Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos** .
    
    <div>
    

    > [!IMPORTANT]  
    > Si el certificado no se muestra en la consola, asegúrese de que no ha seleccionado el usuario o el servicio. Debes seleccionar equipo o no podrás encontrar el certificado de probper.

    
    </div>

9.  Para ver las propiedades del certificado, expanda **certificados**, expanda **personal**y seleccione **certificados**. Seleccione el certificado que desea ver, haga clic con el botón derecho en el certificado y seleccione **abrir**.

10. En la vista del **certificado** , seleccione **detalles**. Desde aquí, puede seleccionar el nombre del sujeto del certificado seleccionando **asunto** y se muestran el nombre del asunto asignado y las propiedades asociadas.

11. Para ver los nombres alternativos del asunto asignados, seleccione **nombre alternativo del asunto**. Se muestran todos los nombres alternativos del asunto asignados. De forma predeterminada, los nombres alternativos de asunto que se encuentran en la propiedad son de tipo **DNS** . Debería ver los siguientes miembros (que deben ser nombres de dominio totalmente cualificados, como se representa en host DNS (si es IPv6 AAAA) los registros:
    
      - Nombre de grupo para este grupo o el nombre de un servidor si no es un grupo
    
      - Nombre del servidor al que está asignado el certificado
    
      - Registros de dirección URL simples, que suelen reunirse y marcar
    
      - Nombres externos de servicios web y internos de servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las opciones seleccionadas en las selecciones del generador de topología y de los servicios web reemplazados.
    
      - Si ya está asignado, la lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.
    
    El último elemento es lo que más le interesa: si existe una lyncdiscover y lyncdiscoverinternal de SAN.
    
    Una vez que tenga esta información, puede cerrar la vista certificado y MMC.

12. Si es un servicio de detección automática, es decir, el lyncdiscover. \>nombre\> de dominio y lyncdiscoverinternal. \<nombre\> de dominio (según se trata de un certificado externo o interno) no se encuentra el nombre alternativo de asunto y está usando un único certificado predeterminado para los tipos predeterminados, WebServicesInternal y WebServiceExternal, haga lo siguiente:
    
      - En el símbolo del sistema del shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Por ejemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para asignar el certificado, escriba lo siguiente:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde "huella digital" es la huella digital que se muestra para el certificado recién emitido.

13. En el caso de que falten nombres alternativos de sujeto de detección automática internos al usar certificados independientes para default, WebServicesInternal y WebServicesExternal, haga lo siguiente:
    
      - En el símbolo del sistema del shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para un nombre alternativo externo de asunto de detección automática, en la línea de comandos, escriba:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para asignar los tipos de certificado individuales, escriba lo siguiente:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde "huella digital" es la huella digital que se muestra para los certificados individuales recién emitidos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

