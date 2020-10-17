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
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502117"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Configuración de certificados para la detección automática en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-12_

Los certificados para el grupo de directores, el grupo de servidores front-end y el proxy inverso requieren entradas de nombre alternativo de sujeto adicionales para admitir conexiones seguras con los clientes de Lync.

<div>


> [!NOTE]  
> Puede usar el cmdlet <STRONG>Get-CsCertificate</STRONG> para ver información sobre los certificados asignados actualmente. Sin embargo, la vista predeterminada trunca las propiedades del certificado y no muestra todos los valores de la propiedad SubjectAlternativeNames. Puede usar los cmdlets <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate y <STRONG>Set-CsCertificate</STRONG> para ver alguna información y solicitar y asignar certificados. Sin embargo, no es el mejor método que hay que usar si no está seguro de las propiedades de los nombres alternativos del sujeto (SAN) sobre el certificado actual. Para ver el certificado y todos los miembros de la propiedad, se recomienda usar el complemento certificados en <EM>Microsoft Management Console (MMC)</EM> o usar el Asistente para la implementación de Lync Server. En el Asistente para la implementación de Lync Server, puede usar el Asistente para certificados para ver las propiedades del certificado. Los procedimientos para ver, solicitar y asignar un certificado mediante el shell de administración de Lync Server y <EM>Microsoft Management Console (MMC)</EM> se detallan en los siguientes procedimientos. Para usar el Asistente para la implementación de Lync Server, vea los detalles aquí si ha implementado el director o el grupo de directores opcional: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure los certificados para el Director en Lync Server 2013</A>. Para el servidor front-end o el grupo de servidores front-end, vea los detalles aquí: <A href="lync-server-2013-configure-certificates-for-servers.md">configurar certificados para servidores en Lync Server 2013</A>.<BR>Los primeros pasos de este procedimiento son los pasos de preparación, para orientarle en cuanto a qué papel juegan los certificados actuales. De forma predeterminada, los certificados no tendrán un lyncdiscover. &lt; sipdomain &gt; o lyncdiscoverinternal. &lt; &gt; entrada de nombre de dominio interno a menos que haya instalado previamente servicios de movilidad o haya preparado los certificados con antelación. Este procedimiento usa el nombre de dominio SIP de ejemplo para 'contoso.com' y el nombre de dominio interno de ejemplo 'contoso.net'.<BR>La configuración de certificado predeterminada para Lync Server 2013 y Lync Server 2010 es usar un único certificado (denominado "predeterminado") con los propósitos predeterminados (para todos los propósitos excepto para los servicios web), WebServicesExternal y WebServicesInternal. Una configuración opcional es usar certificados independientes para cada propósito. Los certificados se pueden administrar con el shell de administración de Lync Server y los cmdlets de Windows PowerShell, o mediante el Asistente para certificados en el Asistente para la implementación de Lync Server.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Para actualizar certificados con nombres alternativos de sujeto nuevos mediante el shell de administración de Lync Server

1.  Inicie sesión en el equipo usando una cuenta con derechos y permisos de administrador

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Averigüe qué certificados se han asignado al servidor y para qué tipo de uso. Esta información es necesaria en el paso siguiente para asignar el certificado actualizado. En la línea de comandos, escriba:
    
        Get-CsCertificate

4.  Compruebe en los resultados del paso anterior si se ha asignado un solo certificado para varios usos o un certificado distinto para cada uso. Mire el parámetro Uso para averiguar cómo se usa un certificado. Compara el parámetro Huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos.

5.  Actualice el certificado. En la línea de comandos, escriba:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por ejemplo, si el cmdlet **Get-CsCertificate** ha mostrado un certificado con uso de Predeterminado, otro con uso de WebServicesInternal y otro con uso de WebServicesExternal, y todos tienen el mismo valor de huella digital, en la línea de comandos, escriba:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Si se asigna un certificado distinto para cada uso (el valor de huella digital es diferente para cada certificado), es importante que no ejecute el cmdlet **Set-CsCertificate** con varios tipos. En este caso, ejecute el cmdlet **Set-CsCertificate** por separado para cada uso. Por ejemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para ver el certificado, haga clic en **Inicio**, **Ejecutar…**. Escriba MMC para abrir Microsoft Management Console.

7.  En el menú de MMC, seleccione **Archivo**, **Agregar o quitar complemento…**, Certificados. Haga clic en **Agregar**. Cuando se le pida, seleccione **Cuenta de equipo** y luego haga clic en **Siguiente**.

8.  Si el certificado está ubicado en este equipo, seleccione **equipo local**. Si el certificado se encuentra en otro PC, seleccione **Otro equipo**, escriba el nombre de dominio completo del PC o haga clic en **Examinar** En **Escriba el nombre de objeto a seleccionar**, escriba el nombre del PC. Haga clic en **Comprobar nombres**. Cuando se resuelva el nombre del equipo, se subrayará. Haga clic en **Aceptar** y luego en **Finalizar**. Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si el certificado no aparece en la consola, asegúrese de que no ha seleccionado usuario o servicio. Debe seleccionar equipo o no podrá ubicar el certificado probper.

    
    </div>

9.  Para ver las propiedades del certificado, expanda **Certificados**, **Personal** y seleccione **Certificados**. Seleccione el certificado que desea ver, haga clic en el certificado y seleccione **Abrir**.

10. En la vista **Certificado**, seleccione **Detalles**. Desde aquí, puede elegir el nombre de sujeto del certificado seleccionando **Sujeto** y se muestran el nombre del sujeto asignado y propiedades asociadas.

11. Para ver los nombres alternativos del sujeto asignados, seleccione **Nombre alternativo del sujeto**. Aparecen todos los nombres alternativos del sujeto asignado. De forma predeterminada, los nombres alternativos del sujeto que se encuentran en la propiedad son de tipo **Nombre de DNS**. Debe ver los siguientes miembros (todos los cuales deben ser nombres de dominio completos representados en los registros del host de DNS (A o, si IPv6 AAAA):
    
      - Nombre del grupo para este grupo o el nombre del servidor si no es un grupo
    
      - Nombre del servidor al que está asignado el certificado
    
      - Registros de direcciones URL simples, normalmente reunión y marcación
    
      - Nombres externos de servicios Web internos y servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el generador de topologías y las selecciones de servicios web invalidadas.
    
      - Si ya está asignado, el lyncdiscover.\<sipdomain\> y lyncdiscoverinternal.\<sipdomain\> registro.
    
    El último elemento es lo que más le interesa; si hay una entrada SAN de lyncdiscover y lyncdiscoverinternal.
    
    Una vez que tenga esta información, puede cerrar la vista de certificado y MMC.

12. Si es un servicio de detección automática, lo que significa lyncdiscover. \> nombre \> de dominio y lyncdiscoverinternal.\<domain name\> (en función de si se trata de un certificado externo o interno) no se encuentra el nombre alternativo del firmante y está usando un único certificado predeterminado para los tipos predeterminados, WebServicesInternal y WebServiceExternal, haga lo siguiente:
    
      - En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe utilizar el parámetro DomainName. Cuando use el parámetro DomainName, debe definir el FQDN para los registros de lyncdiscoverinternal y lyncdiscover. Por ejemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para asignar el certificado, escriba lo siguiente:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde “Huella digital” es la huella digital mostrada para el certificado que acaba de emitir.

13. Cuando faltan los nombres alternativos del sujeto de Detección automática internos al usar certificados separados en Default, WebServicesInternal y WebServicesExternal, haga lo siguiente:
    
      - En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para un nombre alternativo de sujeto del servicio Detección automática externa, en la línea de comandos, escriba:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para asignar tipos de certificados individuales, escriba lo siguiente:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde “Huella digital” es la huella digital mostrada para el certificado individual que acaba de emitir.

</div>

</div>

<span> </span>

</div>

</div>

</div>

