---
title: 'Lync Server 2013: Configurar la compatibilidad para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f10e266674d102b25753aeb58c89a365e7bb8e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Implementar un servidor perimetral o un grupo perimetral es el primer paso para admitir usuarios externos. Para obtener detalles sobre la implementación de servidores perimetrales, consulte [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación. Una consideración importante para la configuración de las directivas es comprender la prioridad de las directivas y cómo se aplican las directivas. La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

Una vez completada la configuración de un servidor perimetral o un grupo perimetral, debe habilitar los tipos de acceso de usuarios externos que desea proporcionar y configurar la configuración del acceso externo. En Lync Server 2013, puede habilitar y configurar directivas y acceso a usuarios externos con el panel de control de Lync Server, el shell de administración de Lync Server o ambos, en función de los requisitos de la tarea.

Para admitir el acceso de usuarios externos, debe hacer lo siguiente:

  - **Habilitar la compatibilidad de su organización**   para habilitar la compatibilidad con el acceso de usuarios externos en su implementación, habilite cada tipo de acceso externo que desee admitir. Para habilitar y deshabilitar el acceso de usuarios externos, puede editar la configuración global o crear y configurar un sitio o una directiva de usuario en la página de la **Directiva de acceso externo** en el grupo **Federación y acceso externo** del panel de control de Lync Server. o bien, mediante el shell de administración de Lync Server y los cmdlets asociados. Los cmdlets para administrar la **Directiva de acceso externo** se encuentran en el tema [Federación y cmdlets de acceso externo en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). Habilitar la compatibilidad con el acceso externo especifica que los servidores que ejecutan el servicio perimetral de acceso de Lync Server admiten comunicaciones con usuarios y servidores externos. Los usuarios internos y externos no pueden comunicarse, mientras que el acceso de usuarios externos está deshabilitado o si aún no se han configurado las directivas para admitirlo.

  - **Configurar y asignar una o más directivas**   para admitir el acceso de usuarios externos, debe configurar directivas para resolver requisitos que incluyen:
    
      - **Directivas de acceso externo**   creadas con un sitio o ámbito de usuario (existe una directiva global de forma predeterminada y no tiene ninguna configuración habilitada). Puede crear y configurar directivas para controlar el uso de uno o varios tipos de acceso de usuarios externos, incluidos los accesos de usuarios federados (incluidos, si se seleccionan, los dominios del XMPP federado), el acceso de usuarios remotos y los proveedores de servicios de mensajería instantánea públicos compatibles. Puede configurar directivas externas en el panel de control de Lync Server mediante la directiva global o una o más directivas de usuario y de sitio creadas administrativamente en la página **Directiva de acceso externo** en el grupo **Federación y acceso externo** . No se puede eliminar la directiva global. Cree y configure cualquier directiva de sitio y de usuario que desee usar para limitar el acceso de usuarios externos a determinados sitios o usuarios. Las directivas globales y de sitio se asignan automáticamente. Si crea y configura una directiva de usuario, debe asignarla a los usuarios específicos mediante la página Configuración de usuario en el panel de control de Lync Server en la página **usuarios** . Busque el usuario o los usuarios a los que desea que se aplique esta directiva y asigne la Directiva. a quién deseas que se apliquen. Para asignar una directiva de usuario configurada a un usuario, consulte [asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Cada directiva de acceso de usuarios externos puede admitir uno o varios de los siguientes elementos: acceso de usuarios remotos, acceso de usuarios federados de SIP, acceso a usuarios federados de XMPP y conectividad de mensajería instantánea pública.
    
      - **Directivas de conferencia**   puede crear y configurar directivas para controlar las conferencias de su organización, incluidos los usuarios de su organización que pueden invitar a usuarios anónimos a las conferencias que hospedan. En la página de **Conferencia** del panel de control de Lync Server están las opciones de directiva en el ámbito global, de sitio y de usuario que controlan la configuración de las conferencias reales. Para obtener más información, vea [administrar reuniones y conferencias en Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Habilite usuarios anónimos para conferencias, usuarios remotos y usuarios federados en la página **configuración de Edge de Access** . La Directiva de la **configuración del límite de acceso** es global en el ámbito. No hay opciones para definir un sitio o una directiva de usuario. El ámbito se controla en la página **Directiva de acceso externo** mediante el uso de la configuración de directivas global, de sitio o de usuario.
        
        Por ejemplo, si desea permitir que los usuarios creen, inviten y administren conferencias con usuarios remotos, debe configurar **Habilitar comunicaciones con usuarios remotos** en la **Directiva de acceso externo** global, sitio o Directiva de usuario, y **Habilitar comunicaciones con usuarios remotos** en la página de **configuración de Edge de Access** . De forma similar, para permitir conferencias con usuarios anónimos o socios federados con los que tenga una relación definida (como los dominios y proveedores federados configurados, la Federación XMPP no admite conferencias), establezca **Habilitar comunicaciones con los usuarios públicos** y **habilitar las comunicaciones con usuarios federados** en la Directiva de **acceso externo** , sitio global, sitio o Directiva de usuario. Después, seleccione Configuración de directiva gratuita global **para habilitar el acceso de usuarios anónimos a las conferencias** y **Habilitar la conectividad de mensajería instantánea pública y federada** en la página de **configuración de Edge de Access** .

Puede configurar la configuración de acceso de usuarios externos, incluidas las directivas que desee usar para controlar el acceso de usuarios externos, incluso si no ha habilitado el acceso de usuarios externos para su organización. Sin embargo, las directivas y otras opciones de configuración que se configuran solo estarán vigentes cuando tenga habilitado el acceso de usuarios externos a su organización. Los usuarios externos no pueden comunicarse con los usuarios de su organización cuando el acceso de usuarios externos está deshabilitado o si ninguna directiva de acceso de usuarios externos está configurada para admitirlo.

La implementación de Edge autentica los tipos de usuarios externos (excepto para los usuarios anónimos, que son autenticados por el identificador de conferencia y una clave de paso que se envía al participante anónimo al crear la Conferencia e invitar a participantes) y controles acceso según la configuración de la compatibilidad de los extremos. Para controlar las comunicaciones, puede configurar una o varias directivas y configurar opciones que definan cómo los usuarios de dentro y fuera de la implementación se comunican entre sí. Las directivas y la configuración incluyen la directiva global predeterminada para el acceso de usuarios externos, además de las directivas de sitio y de usuario que puede crear y configurar para habilitar uno o varios tipos de acceso de usuarios externos para determinados sitios o usuarios.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Habilitar y deshabilitar el acceso anónimo de usuarios en Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

