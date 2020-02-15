---
title: 'Lync Server 2013: configuración de conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31224e145fc5fea1623b0236b87ae9cdec3f82b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Configuración de la conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, no puede usar al Asistente para la implementación de Lync Server para solicitar el certificado. En su lugar, realice los pasos del siguiente procedimiento.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Configuración de la conectividad de mensajería instantánea pública

1.  En un servidor front-end, abra el Generador de topologías. Expanda grupos perimetrales y, a continuación, haga clic con el botón secundario en el servidor perimetral o grupo de servidores perimetrales. Seleccione Editar propiedades.

2.  En Editar propiedades en General, seleccione Habilitar federación para este grupo de servidores perimetrales (Puerto 5061). Haga clic en Aceptar.

3.  Haga clic en Acción, seleccione Topología y, finalmente, Publicar. Cuando se le solicite en Publicar la topología, seleccione Siguiente. Una vez completado el proceso de publicación, haga clic en Finalizar.

4.  En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en Instalar o en Actualizar Lync Server System y, a continuación, en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar nuevamente.

5.  En los componentes de Lync Server de instalación, haga clic en Siguiente. La pantalla de resumen mostrará las acciones que se ejecutan. Una vez que se termine la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para que admita la conectividad de mensajería instantánea pública con AOL

1.  Cuando la plantilla requerida está disponible para la entidad emisora de certificados, utilice el siguiente cmdlet de Windows PowerShell de en el servidor perimetral para solicitar el certificado
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    El nombre de certificado predeterminado de la plantilla usada para Lync Server es servidor Web. Especifique el nombre \<\> de la plantilla solo si necesita usar una plantilla que sea diferente de la plantilla predeterminada.
    
    <div>
    

    > [!IMPORTANT]  
    > Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe usar Windows PowerShell en lugar del Asistente para certificados para solicitar que el certificado se asigne al perímetro externo para el servicio perimetral de acceso. Esto es porque la plantilla de la entidad emisora de certificados (CA) de servidor Web que utiliza el Asistente para certificados para solicitar un certificado no es compatible con la configuración del cliente de EKU. Antes de usar Windows PowerShell para crear el certificado, el administrador de la entidad de certificación debe crear e implementar una nueva plantilla que admita EKU de cliente.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

