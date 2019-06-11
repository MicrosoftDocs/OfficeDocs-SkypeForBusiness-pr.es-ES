---
title: 'Lync Server 2013: Configurar directivas para controlar el acceso de usuarios públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e259082aa73d4354e8e4aa93eb7a0cc8d7ed7a6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La conectividad de mensajería instantánea pública (mi) permite a los usuarios de la organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería\!instantánea pública, como Windows Live Network de servicios de Internet, Yahoo y AOL. Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios públicos pueden colaborar con usuarios internos de Lync Server. La conectividad de mensajería instantánea pública es una característica agregada que se basa en la configuración de la implementación y los usuarios. También depende del suministro del servicio en el proveedor de mensajería instantánea pública. Para obtener más información sobre cómo aprovisionar su implementación para usar los proveedores públicos, consulte la guía de aprovisionamiento de la conectividad de mensajería instantánea pública para Microsoft Lync Server, Office Communications Server y Live Communications Server.[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</P></LI></UL>



</div>

Para acceder al sitio de aprovisionamiento de la conectividad de mensajería instantánea pública de Microsoft Lync Server, use el siguiente vínculo:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

Para controlar el acceso de los usuarios públicos, puede configurar directivas en el nivel global, de sitio y de usuario. Para obtener más información sobre los tipos de directivas que puede configurar, vea [configurar la compatibilidad del acceso de usuarios externos en Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) en la documentación de implementación o en la documentación de planeación. La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software de cliente. La solicitud se acepta a menos que los remitentes externos se bloquean explícitamente mediante una regla configurada por el usuario (es decir, la configuración de las listas **permitir** o **bloquear** del cliente del usuario). Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario decide bloquear todos los mensajes instantáneos de usuarios que no estén **** en su lista de permitidos.

<div>


> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios públicos, incluso si no ha habilitado la Federación de su organización. Sin embargo, las directivas que configure solo estarán vigentes cuando tenga habilitada la Federación de su organización. Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones. Además, si especifica una directiva de usuario para controlar el acceso de los usuarios públicos, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server y que usan la Directiva. Para obtener detalles sobre cómo especificar usuarios públicos que pueden iniciar sesión en Lync Server, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync server 2013</A> en la documentación de implementación o en la documentación de operaciones.



</div>

Use el procedimiento siguiente para configurar una directiva que admita el acceso de usuarios de uno o más proveedores de mensajería instantánea pública.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar una directiva de acceso externo para admitir el acceso de usuarios públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , realice una de las siguientes acciones:
    
      - Para configurar la directiva global para admitir el acceso de usuarios públicos, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una nueva Directiva de sitio, haga clic en **nueva**y, a continuación, haga clic en **Directiva del sitio**. En **seleccionar un sitio**, haga clic en el sitio adecuado de la lista y, a continuación, haga clic en **Aceptar**.
    
      - Para crear una nueva Directiva de usuario, haga clic en **nueva**y, a continuación, haga clic en **Directiva de usuario**. En **nueva Directiva de acceso externo**, cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnablePublicUsers** para una directiva de usuario que permita la comunicación para usuarios públicos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  Faculta Si desea agregar o editar una descripción, especifique la información de la Directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios públicos para la Directiva, active la casilla **Habilitar comunicaciones con usuarios públicos** .
    
      - Para deshabilitar el acceso de usuarios públicos para la Directiva, desactive la casilla **Habilitar comunicaciones con usuarios públicos** .

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios públicos, también debe habilitar la compatibilidad con la Federación de su organización. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Si se trata de una directiva de usuario, también debe aplicar la Directiva a los usuarios públicos que desee que puedan colaborar con los usuarios públicos. Para obtener más información, consulte [asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o editar proveedores federados de SIP públicos en Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

