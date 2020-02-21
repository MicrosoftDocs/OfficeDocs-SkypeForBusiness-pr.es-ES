---
title: 'Lync Server 2013: configuración de la compatibilidad para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94250ec0fbae3a7077e545eebdc848db3c370d19
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Configuración de la compatibilidad para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La implementación de un servidor perimetral o de un grupo de servidores perimetrales es el primer paso para la compatibilidad con usuarios externos. Para obtener más información sobre la implementación de servidores perimetrales, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación. Un punto importante que debe tener en cuenta para la configuración de directivas es el orden de prioridad de las directivas y la aplicación de las mismas. La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más cerca esté la configuración de la Directiva, el objeto al que afecta la Directiva, más influencia tendrá en el objeto.

Una vez configurado el servidor perimetral o grupo de servidores perimetrales, debe habilitar los tipos de acceso de usuarios externos que desea admitir y configurar la compatibilidad para el acceso externo. En Lync Server 2013, habilite y configure las directivas y el acceso de usuarios externos mediante el panel de control de Lync Server, el shell de administración de Lync Server o ambos, en función de los requisitos de la tarea.

Para la compatibilidad para el acceso de usuarios externos, debe realizar las dos acciones siguientes:

  - **Habilite la compatibilidad de su organización**   para permitir el acceso de usuarios externos en la implementación, habilite todos los tipos de acceso externo que desee admitir. La compatibilidad con el acceso de usuarios externos se habilita y deshabilita editando la configuración global o creando y configurando una directiva de usuario o sitio en la página **Directiva de acceso externo** en el grupo **Federación y acceso externo** del panel de control de Lync Server o mediante el shell de administración de Lync Server y los cmdlets asociados. Los cmdlets para administrar la **Directiva de acceso externo** se encuentran en los [cmdlets Federación de temas y acceso externo en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). Al habilitar la compatibilidad con acceso externo, se especifica que los servidores que ejecutan el servicio perimetral de acceso de Lync Server admiten comunicaciones con usuarios y servidores externos. Los usuarios internos y externos no pueden comunicarse mientras el acceso de usuarios externos está deshabilitado o si todavía no se han configurado las directivas para que lo admitan.

  - **Configurar y asignar una o más directivas**   para admitir el acceso de usuarios externos, configure las directivas para solucionar los requisitos que incluyen:
    
      - **Las directivas**   de acceso externo creadas con un ámbito de sitio o de usuario (existe una directiva global de forma predeterminada y no tienen ninguna configuración habilitada). Las directivas se crean y se configuran para controlar el uso de uno o varios tipos de acceso de usuarios externos, incluidos el acceso de usuarios federados (incluidos, si se selecciona, los dominios de XMPP federados) y los proveedores de servicios de mensajería instantánea públicos admitidos. Configure directivas externas en el panel de control de Lync Server mediante la directiva global o una o más directivas de usuario y de sitio creadas administrativamente, en la página **Directiva de acceso externo** del grupo **Federación y acceso externo** . La directiva global no puede eliminarse. Cree y configure las directivas de sitio y de usuario que desee usar para limitar el acceso de usuarios externos para sitios o usuarios específicos. Las directivas globales y de sitio se asignan automáticamente. Si crea y configura una directiva de usuario, debe asignarla a los usuarios específicos mediante la página Configuración de usuario en el panel de control de Lync Server en la página **usuarios** . Busque el usuario o los usuarios a los que desea que se aplique esta directiva y asígnele la Directiva. al que desea que se aplique. Para asignar una directiva de usuario configurada a un usuario, consulte [asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Cada directiva de acceso de usuarios externos puede admitir uno o varios de los siguientes elementos: acceso de usuarios remotos, acceso de usuarios federados de SIP, acceso de usuarios federados de XMPP y conectividad de mensajería instantánea pública.
    
      - **Directivas de conferencia**   puede crear y configurar directivas para controlar la Conferencia en su organización, incluidos los usuarios de su organización que pueden invitar a usuarios anónimos a las conferencias que hospedan. En la página de **Conferencia** del panel de control de Lync Server hay configuraciones de directiva en el ámbito global, de sitio y de usuario que controlan la configuración de las conferencias reales. Para obtener más información, consulte [administrar reuniones y conferencias en Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Puede habilitar a los usuarios anónimos para mantener conferencias, usuarios remotos y usuarios federados en la página **Configuración perimetral de acceso**. La directiva de la **Configuración perimetral de acceso** es de ámbito global. No existen opciones para definir una directiva de sitio o usuario. El ámbito se controla en la página **Directiva de acceso externo** mediante el uso de configuraciones de directivas globales, de sitio o de usuario.
        
        Por ejemplo, si desea permitir a los usuarios crear, invitar y administrar conferencias con usuarios remotos, debe configurar **Habilitar comunicaciones con usuarios remotos** en la directiva **Directiva de acceso externo** global, de sitio o de usuario y **Habilitar comunicaciones con usuarios remotos** en la página **Configuración perimetral de acceso**. Igualmente, para permitir las conferencias con usuarios anónimos o socios federados con los que haya definido una relación (como proveedores y dominios SIP federados configurados, la federación XMPP no es compatible con la función de conferencia), defina **Habilitar comunicaciones con usuarios públicos** y **Habilitar comunicaciones con usuarios federados** en la directiva **Directiva de acceso externo** global, de sitio o de usuario. A continuación, seleccione las opciones de directiva global complementarias **Habilitar acceso de usuario anónimo a las conferencias** y **Habilitar federación y conectividad de mensajería instantánea pública** en la página **Configuración perimetral de acceso**.

Puede configurar parámetros de acceso de usuarios externos, incluidas las directivas que desea usar para controlar el acceso de usuarios externos, aunque no haya habilitado el acceso de usuarios externos en su organización. Sin embargo, tanto las directivas como otros parámetros que se configuran solo son efectivos cuando se habilita el acceso de usuarios externos en su organización. Los usuarios externos no pueden comunicarse con usuarios de su organización cuando el acceso de usuarios externos está deshabilitado o no se han configurado directivas de acceso de usuarios externos para admitir dichas comunicaciones.

La implementación perimetral sirve para autenticar los tipos de usuarios externos (excepto los usuarios anónimos, que se autentican mediante el Id. de conferencia y una contraseña que se envía al participante anónimo cuando se crea la conferencia y se invita a los participantes) y controlar el acceso según cómo se haya configurado la compatibilidad perimetral. Para controlar las comunicaciones, puede configurar una o más directivas y otros parámetros que sirvan para definir el modo en que se comunican los usuarios de dentro y fuera de la implementación. Eso incluye la directiva global predeterminada para el acceso de usuarios externos, además de las directivas de sitio y usuario que puede crear y configurar para habilitar uno o más tipos de acceso de usuarios externos para sitios o usuarios específicos.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Habilitar o deshabilitar el acceso de usuarios anónimos en Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

