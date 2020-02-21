---
title: 'Lync Server 2013: configurar directivas para controlar el acceso de usuarios públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54c92e1da5ea1ea54ae8386cdcdce5054d76609e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La conectividad de mensajería instantánea pública permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por los proveedores de servicios de mensajería instantánea pública\!, incluida la red de Windows Live de servicios de Internet, Yahoo y AOL. Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios públicos pueden colaborar con usuarios internos de Lync Server. La conectividad de mensajería instantánea pública es una característica agregada que se basa en la configuración de la implementación y los usuarios. También depende del aprovisionamiento del servicio en el proveedor de mi pública. Para obtener información sobre cómo aprovisionar la implementación para usar los proveedores públicos, consulte la guía de aprovisionamiento de la conectividad de mensajería instantánea pública para Microsoft Lync Server, Office Communications Server y Live Communications Server.[https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</P></LI></UL>



</div>

Para obtener acceso al sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Microsoft Lync Server, use el siguiente vínculo:[https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)

Puede configurar directivas de nivel global, de sitio y de usuario para controlar el acceso de usuarios públicos. Para obtener más información sobre los tipos de directivas que puede configurar, consulte [Configuring Support for external User Access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) en la documentación sobre implementación o la documentación referente a la planeación. La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más cerca esté la configuración de la Directiva, el objeto al que afecta la Directiva, más influencia tendrá en el objeto.

En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software cliente. Se acepta la solicitud a menos que los remitentes externos queden explícitamente bloqueados por una regla configurada por el usuario (es decir, la configuración de las listas **Permitir** y **Bloquear** del cliente del usuario). Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario opta por bloquear todos los mensajes instantáneos de los usuarios que no estén en su lista **Permitir**.

<div>


> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios públicos, incluso aunque no haya habilitado una federación para la organización. Sin embargo, las directivas que configure únicamente surtirán efecto cuando haya habilitado la federación en la organización. Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones. Además, si especifica una directiva de usuario para controlar el acceso de los usuarios públicos, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server y que están configurados para usar la Directiva. Para obtener información detallada sobre cómo especificar usuarios públicos que pueden iniciar sesión en Lync Server, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync server 2013</A> en la documentación de implementación o en la documentación de operaciones.



</div>

Use el procedimiento que se describe a continuación para configurar una directiva que admita el acceso de usuarios de uno o varios proveedores de mensajería instantánea pública.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar una directiva de acceso externo para permitir el acceso de usuarios públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.

4.  En la página  **Directiva de acceso externo **, siga uno de estos procedimientos:
    
      - Para configurar la directiva global para permitir el acceso de usuarios públicos, haga clic en la directiva global, en  **Editar ** y en  **Mostrar detalles **.
    
      - Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.
    
      - Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **EnablePublicUsers** para una directiva de usuario que permita comunicaciones para usuarios públicos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en  **Editar ** y, a continuación en  **Mostrar detalles **.

5.  (Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.

6.  Siga uno de estos procedimientos:
    
      - Para habilitar el acceso de usuarios públicos para la directiva, active la casilla  **Habilitar comunicaciones con usuarios públicos **.
    
      - Para deshabilitar el acceso de usuarios públicos para la directiva, desactive la casilla  **Habilitar comunicaciones con usuarios públicos **.

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios públicos, también debe permitir la federación en su organización. Para obtener más información, consulte [Configure Policies to control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Si se trata de una directiva de usuario, también tiene que aplicar la directiva a los usuarios públicos que desee que puedan colaborar con usuarios públicos. Para obtener más información, consulte [asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Consulta también


[Crear o editar proveedores federados de SIP públicos en Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

