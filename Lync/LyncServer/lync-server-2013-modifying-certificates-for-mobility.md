---
title: 'Lync Server 2013: modificación de certificados para movilidad'
description: 'Lync Server 2013: modificación de certificados para movilidad.'
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
ms.openlocfilehash: 099122b1773c3f15d8ae0034ee5fa404225cdfd2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555856"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Modificación de certificados para movilidad en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-20_

Para admitir conexiones seguras entre el entorno de Lync y los clientes móviles, los certificados de capa de sockets seguros (SSL) para el grupo de directores, el grupo de servidores front-end y el proxy inverso deben actualizarse con algunas entradas de nombre alternativo de sujeto (SAN) adicionales. Si necesita consultar más detalles sobre los requisitos de certificados para la movilidad, consulte la sección requisitos [técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), pero básicamente necesitará obtener nuevos certificados de la entidad de certificación con las entradas de San adicionales incluidas y, a continuación, agregar dichos certificados con los pasos de este artículo.

Por supuesto, antes de empezar, suele ser una buena idea conocer los nombres de sujeto alternativos que ya tienen los certificados. Si no está seguro de lo que ya está configurado, hay muchas formas de averiguarlo. Mientras que la opción se encuentra ahí para ejecutar **Get-CsCertificate** y otros comandos de PowerShell para ver esta información, (que analizaremos a continuación) de forma predeterminada, los datos se truncarán, por lo que es posible que no vea todas las propiedades que necesita. Para obtener un buen vistazo al certificado y a todas sus propiedades, puede ir a Microsoft Management Console (MMC) y cargar el complemento certificados (que también trataremos a continuación), o puede simplemente comprobar el Asistente para la implementación de Lync Server.

Como se indicó anteriormente, los pasos siguientes le guiarán por el proceso de actualización de los certificados mediante el shell de administración de Lync Server y MMC. Si está interesado en usar el Asistente para certificados en el Asistente para la implementación de Lync Server en su lugar, puede comprobar la [configuración de certificados del Director en Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para el director o el grupo de directores, si ha configurado uno (es posible que no tenga). Para el servidor front-end o el grupo de servidores front-end, querrá ver [configurar certificados para servidores en Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

Un último aspecto que se debe tener en cuenta es que puede tener un único certificado predeterminado en el entorno de Lync Server 2013 o puede tener certificados independientes para el valor predeterminado (que es todo excepto los servicios web), WebServicesExternal y WebServicesInternal. Independientemente de la configuración, estos pasos deben ayudarle.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Para actualizar certificados con nombres alternativos de sujeto nuevos mediante el shell de administración de Lync Server

1.  Debe iniciar sesión en el servidor de Lync Server 2013 con una cuenta que tenga derechos y permisos de administrador local. Además, si está ejecutando la **solicitud-CsCertificate** de PowerShell en los pasos 12 y posteriores, la cuenta debe tener derechos para la entidad de certificación especificada (CA).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Antes de poder asignar un certificado actualizado, deberá averiguar qué certificados se han asignado al servidor y para qué tipo de uso. En la línea de comandos, escriba lo siguiente:
    
        Get-CsCertificate

4.  Revise el resultado del paso anterior para ver si un único certificado se ha asignado para varios usos o si se ha asignado un certificado diferente para cada uso. Busque en el parámetro use para averiguar cómo se usa un certificado. Compara el parámetro Huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos. Mantenga el ojo del parámetro Thumbprint.

5.  Actualice el certificado. En la línea de comandos, escriba:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por ejemplo, si el cmdlet **Get-CsCertificate** muestra un certificado con uso predeterminado, otro con uso de WebServicesInternal y otro con uso de WebServicesExternal, y todos tenían el mismo valor de huella digital, en la línea de comandos debe escribir:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Si se asigna un certificado independiente para cada uso (por lo que el valor de la huella digital que ha comprobado arriba es diferente para cada certificado), es fundamental que **no** ejecute el cmdlet **set-CsCertificate** con varios tipos, como en el ejemplo anterior. En este caso, ejecute el cmdlet **Set-CsCertificate** por separado para cada uso. Por ejemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para ver el certificado (o certificados), haga clic en **Inicio**, haga clic en **Ejecutar...**. Escriba MMC para abrir Microsoft Management Console.

7.  En el menú de MMC, seleccione **Archivo**, **Agregar o quitar complemento…**, Certificados. Haga clic en **Agregar**. Cuando se le pida, seleccione **Cuenta de equipo** y luego haga clic en **Siguiente**.

8.  Si este es el servidor en el que se encuentra el certificado, seleccione **equipo local**. Si el certificado está ubicado en otro equipo, debe seleccionar **otro equipo**y, a continuación, puede escribir el nombre de dominio completo del equipo, o bien hacer clic en **examinar** en **Escriba el nombre de objeto a seleccionar**y escribir el nombre del equipo. Haga clic en **Comprobar nombres**. Cuando se resuelva el nombre del equipo, se mostrará subrayado. Haga clic en **Aceptar** y luego en **Finalizar**. Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos**.

9.  Para ver las propiedades del certificado, expanda **Certificados**, **Personal** y seleccione **Certificados**. Seleccione el certificado que desea ver, haga clic en el certificado y seleccione **Abrir**.

10. En la vista **Certificado**, seleccione **Detalles**. Desde aquí, puede elegir el nombre de sujeto del certificado seleccionando **Sujeto** y se muestran el nombre del sujeto asignado y propiedades asociadas.

11. Para ver los nombres alternativos del sujeto asignados, seleccione **Nombre alternativo del sujeto**. Todos los nombres alternativos de sujeto asignados se muestran aquí. Los nombres alternativos de sujeto que se encuentran aquí son del tipo **nombre DNS** de forma predeterminada. Debe ver los siguientes miembros (todos los cuales deben ser nombres de dominio completos representados en los registros del host de DNS (A o, si IPv6 AAAA):
    
      - Nombre de grupo para este grupo o el nombre de servidor único si no se trata de un grupo de servidores
    
      - Nombre del servidor al que está asignado el certificado
    
      - Registros de direcciones URL simples, normalmente reunión y marcación
    
      - Nombres externos de servicios Web internos y servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el generador de topologías y las selecciones de servicios web invalidadas.
    
      - Si ya está asignado, el lyncdiscover.\<sipdomain\> y lyncdiscoverinternal.\<sipdomain\> registro.
    
    El último elemento es lo que más le interesa: si hay una entrada de SAN de lyncdiscover y lyncdiscoverinternal.
    
    Repita estos pasos si tiene varios certificados que comprobar. Una vez que tenga esta información, puede cerrar la vista de certificado y MMC.

12. Si falta un nombre alternativo del sujeto del servicio Detección automática, realice lo siguiente:
    
      - En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Cuando usa el parámetro DomainName, tiene que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Por ejemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para asignar el certificado, escriba lo siguiente:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde “Huella digital” es la huella digital mostrada para el certificado que acaba de emitir.

13. Para que falte un SAN de detección automática interna cuando use certificados independientes para default, WebServicesInternal y WebServicesExternal, haga lo siguiente:
    
      - En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Cuando usa el parámetro DomainName, tiene que usar un prefijo adecuado para el FQDN de dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para un nombre alternativo de sujeto del servicio Detección automática externa, en la línea de comandos, escriba:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Cuando usa el parámetro DomainName, tiene que usar un prefijo adecuado para el FQDN de dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para asignar tipos de certificados individuales, escriba lo siguiente:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde “Huella digital” es la huella digital mostrada para el certificado individual que acaba de emitir.
    
    <div>
    

    > [!NOTE]  
    > Solo para tener en cuenta, los pasos 12 y 13 solo deben ejecutarse si la cuenta que los ejecuta tiene acceso a la entidad de certificación con los permisos adecuados. Si no puede iniciar sesión con una cuenta que tiene estos permisos, o si está usando una entidad de certificación pública o remota para los certificados, necesitará solicitarlos mediante el Asistente para la implementación de Lync Server, que se ha tocado en la parte superior del artículo.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

