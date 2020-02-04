---
title: 'Lync Server 2013: Modificación de certificados para movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Modificación de certificados para movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-20_

Para admitir conexiones seguras entre su entorno de Lync y sus clientes móviles, los certificados de nivel de socket seguro (SSL) para el grupo de directores, el grupo front-end y el proxy inverso deben actualizarse con un nombre alternativo de asunto adicional ( SAN). Si necesita consultar más detalles sobre los requisitos de certificados para la movilidad, consulte la sección requisitos técnicos de la [movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), pero básicamente tendrá que obtener nuevos certificados de la entidad emisora de certificados con las entradas de San adicionales incluidas y, después, agregar esos certificados siguiendo los pasos de este artículo.

Por supuesto que antes de empezar, suele ser una buena idea saber qué nombres alternativos de sujeto ya tienen los certificados. Si no está seguro de lo que ya está configurado, hay muchas formas de averiguarlo. Si bien la opción está allí para ejecutar **Get-CsCertificate** y otros comandos de PowerShell para ver esta información, (que trataremos a continuación) de forma predeterminada, se truncarán los datos, por lo que es posible que no vea todas las propiedades que necesita. Para obtener un buen aspecto del certificado y de todas sus propiedades, puede ir a Microsoft Management Console (MMC) y cargar el complemento certificados (que también trataremos a continuación), o bien, puede simplemente comprobar el Asistente para la implementación de Lync Server.

Como se mencionó anteriormente, los pasos siguientes le guiarán en la actualización de certificados mediante el shell de administración de Lync Server y MMC. Si está interesado en usar el Asistente para certificados en el Asistente para la implementación de Lync Server, en su lugar, puede comprobar la [configuración de certificados para el director de Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para el grupo de directores o directores, si ha configurado uno (es posible que no lo tenga). Para el servidor front-end o el grupo front-end, querrá ver [configurar certificados para servidores en Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

Un último aspecto que se debe tener en cuenta es que puede tener un único certificado predeterminado en el entorno de Lync Server 2013, o puede que tenga certificados separados de forma predeterminada (que es todo menos los servicios web), WebServicesExternal y WebServicesInternal. Independientemente de la configuración, estos pasos le ayudarán.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Para actualizar certificados con nombres alternativos de asunto nuevos mediante el shell de administración de Lync Server

1.  Debe iniciar sesión en su servidor de Lync Server 2013 con una cuenta que tenga derechos y permisos de administrador local. Además, si está ejecutando el CsCertificate de **solicitud** de PowerShell en los pasos 12 y posteriores, la cuenta debe tener derechos para la entidad emisora de certificados especificada (CA).

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Antes de poder asignar un certificado actualizado, tendrá que averiguar qué certificados se han asignado al servidor y para qué tipo de uso. En la línea de comandos, escriba:
    
        Get-CsCertificate

4.  Revise la salida del paso anterior para ver si se ha asignado un certificado para varios usos, o si se ha asignado un certificado diferente para cada uso. Busque el parámetro use para saber cómo se usa un certificado. Compare el parámetro de la huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos. Mantén el ojo del parámetro de la huella digital.

5.  Actualice el certificado. En la línea de comandos, escriba:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por ejemplo, si el cmdlet **Get-CsCertificate** muestra un certificado con el uso predeterminado, otro con el uso de WebServicesInternal y otro con el uso de WebServicesExternal, y todos tenían el mismo valor de huella digital, en la línea de comandos, debe escribir:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Si se asigna un certificado independiente para cada uso (por lo que el valor de la huella digital que ha activado anteriormente es diferente para cada certificado), es fundamental que **no** ejecute el cmdlet **set-CsCertificate** con varios tipos, como en el ejemplo anterior. En este caso, ejecute el cmdlet **set-CsCertificate** por separado para cada uso. Por ejemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para ver el certificado (o certificados), haga clic en **Inicio**, haga clic en **Ejecutar...**. Escriba MMC para abrir la consola de administración de Microsoft.

7.  En el menú MMC, seleccione **archivo**, seleccione **Agregar o quitar complemento...**, seleccione certificados. Haga clic en **Agregar**. Cuando se le solicite, seleccione **cuenta de equipo**y, a continuación, haga clic en **siguiente**.

8.  Si este es el servidor donde se encuentra el certificado, seleccione **equipo local**. Si el certificado se encuentra en otro equipo, debe seleccionar **otro equipo**y, a continuación, puede escribir el nombre de dominio completo del equipo o hacer clic en **examinar** , escriba el nombre de **objeto que desea seleccionar**y escriba el nombre del equipo. Haga clic en **Comprobar nombres**. Cuando se resuelva el nombre del equipo, aparecerá subrayado. Haga clic en **Aceptar**y, después, en **Finalizar**. Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos** .

9.  Para ver las propiedades del certificado, expanda **certificados**, expanda **personal**y seleccione **certificados**. Seleccione el certificado que desea ver, haga clic con el botón derecho en el certificado y seleccione **abrir**.

10. En la vista del **certificado** , seleccione **detalles**. Desde aquí, puede seleccionar el nombre del sujeto del certificado seleccionando **asunto** y se muestran el nombre del asunto asignado y las propiedades asociadas.

11. Para ver los nombres alternativos del asunto asignados, seleccione **nombre alternativo del asunto**. Aquí se muestran todos los nombres alternativos del asunto asignados. Los nombres alternativos de asunto que se encuentran aquí son de tipo **DNS** de forma predeterminada. Debería ver los siguientes miembros (que deben ser nombres de dominio totalmente cualificados, como se representa en host DNS (si es IPv6 AAAA) los registros:
    
      - Nombre de grupo para este grupo o el nombre de servidor único si no se trata de un grupo
    
      - Nombre del servidor al que está asignado el certificado
    
      - Registros de dirección URL simples, que suelen reunirse y marcar
    
      - Nombres externos de servicios web y internos de servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las opciones seleccionadas en las selecciones del generador de topología y de los servicios web reemplazados.
    
      - Si ya está asignado, la lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.
    
    El último elemento es lo que te interesa más interesado: si hay una lyncdiscover y lyncdiscoverinternal de SAN.
    
    Repita estos pasos si tiene varios certificados para comprobar. Una vez que tenga esta información, puede cerrar la vista certificado y MMC.

12. Si falta un nombre alternativo de asunto del servicio de detección automática y está usando un único certificado predeterminado para los tipos predeterminados, WebServicesInternal y WebServiceExternal, haga lo siguiente:
    
      - En el símbolo del sistema del shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Cuando use el parámetro DomainName, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Por ejemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para asignar el certificado, escriba lo siguiente:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde "huella digital" es la huella digital que se muestra para el certificado recién emitido.

13. Para una SAN interna de detección automática que falta al usar certificados independientes para default, WebServicesInternal y WebServicesExternal, haga lo siguiente:
    
      - En el símbolo del sistema del shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Cuando use el parámetro DomainName, tendrá que usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para un nombre alternativo externo de asunto de detección automática, en la línea de comandos, escriba:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Cuando use el parámetro DomainName, tendrá que usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para asignar los tipos de certificado individuales, escriba lo siguiente:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde "huella digital" es la huella digital que se muestra para los certificados individuales recién emitidos.
    
    <div>
    

    > [!NOTE]  
    > Solo para tener en cuenta, los pasos 12 y 13 solo se deben ejecutar si la cuenta que los ejecuta tiene acceso a la entidad emisora de certificados con los permisos adecuados. Si no puede iniciar sesión con una cuenta que tiene esos permisos, o si usa una entidad emisora de certificados pública o remota para sus certificados, necesitará solicitarlos mediante el Asistente para la implementación de Lync Server, que se ha tocado en la parte superior de la Knowledge.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

