---
title: 'Lync Server 2013: Establecer conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Establecer conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Si su organización desea admitir la conectividad de mensajería instantánea (mi) pública con AOL, no puede usar el Asistente para la implementación de Lync Server para solicitar el certificado. En su lugar, realice los pasos del procedimiento siguiente.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Configuración de la conectividad de mensajería instantánea pública

1.  En un servidor front-end, abra Topology Builder. Expanda agrupaciones perimetrales y haga clic con el botón derecho en el servidor perimetral o en el grupo de servidores perimetrales. Seleccione Editar propiedades.

2.  En propiedades de edición, en general, seleccione Habilitar Federación para este grupo perimetral (puerto 5061). Haga clic en Aceptar.

3.  Haga clic en acción, seleccione topología, seleccione publicar. Cuando se le solicite al publicar la topología, haga clic en siguiente. Una vez finalizada la publicación, haga clic en finalizar.

4.  En el servidor perimetral, abra el Asistente para la implementación de Lync Server. Haga clic en instalar o actualizar el sistema Lync Server y, a continuación, haga clic en configurar o quitar los componentes de Lync Server. Vuelva a hacer clic en ejecutar.

5.  En instalación de los componentes de Lync Server, haga clic en siguiente. La pantalla resumen mostrará las acciones a medida que se ejecutan. Una vez que haya finalizado la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en finalizar para completar la implementación.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para admitir la conectividad de mensajería instantánea pública con AOL

1.  Cuando la plantilla requerida esté disponible para la CA, use el siguiente cmdlet de Windows PowerShell de en el servidor perimetral para solicitar el certificado.
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    El nombre de certificado predeterminado de la plantilla usada para Lync Server es servidor Web. Especifique el nombre \<\> de la plantilla únicamente si necesita usar una plantilla distinta de la predeterminada.
    
    <div>
    

    > [!IMPORTANT]  
    > Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe usar Windows PowerShell en lugar del asistente de certificados para solicitar que el certificado se asigne al borde externo del servicio perimetral de acceso. Esto se debe a que la plantilla de servidor Web de la entidad de certificación (CA) que usa el Asistente para solicitar un certificado no admite la configuración de EKU de cliente. Antes de usar Windows PowerShell para crear el certificado, el administrador de la CA debe crear e implementar una nueva plantilla que admita EKU de cliente.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

