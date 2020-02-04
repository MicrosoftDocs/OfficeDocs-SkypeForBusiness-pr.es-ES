---
title: 'Lync Server 2013: consideraciones de migración para reuniones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Consideraciones de migración para las reuniones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-10_

En esta sección se tratan los temas siguientes:

  - Cambios en las reuniones de Microsoft Lync Server 2013

  - Migrar usuarios en función de sus necesidades de conferencia

  - Migrar reuniones y contenido de reuniones existentes

  - Experiencia del usuario durante la migración de Lync Server 2010

  - Experiencia del usuario durante la migración de Office Communications Server 2007 R2

  - Compatibilidad de Microsoft Lync 2013 con reuniones en versiones anteriores de un servidor

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Cambios en las reuniones de Lync Server 2013

**Características de Lync Server 2013.**    Lync Server 2013 proporciona nuevas características de conferencia que estarán disponibles para los usuarios después de que sus cuentas se muevan a Lync Server 2013 y que inicien sesión con el cliente de Lync 2013. Las nuevas características se describen en [las nuevas características de conferencia de Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Dirección URL de la reunión.**    Al igual que en lync Server 2010, todas las reuniones recién programadas en lync Server 2013 tienen un prefijo de dirección URL de https://y las reuniones existentes se migran con las cuentas de usuario. Sin embargo, Lync Server 2013 no admite la llamada de conferencia de Office Communications Server 2007 R2 (Prefijo de URL de conf://) o la conferencia web (Prefijo de dirección URL de meet://). Para obtener más información, vea "migrar reuniones de Office Communications Server 2007 R2" más adelante en este tema.

**Compatibilidad con clientes.**    A diferencia de lync Server 2010, lync Server 2013 no es compatible con los clientes de Office Communicator para conferencias. No puede usar los siguientes clientes para unirse a reuniones programadas a través del complemento de reuniones en línea para Lync 2013:

  - Office Communicator 2007 R2

  - Operador de Microsoft Office Communications Server 2007 R2

  - Office Communicator 2007

  - Office Live Meeting 2007

Durante la migración, los usuarios de Office Communicator 2007 R2 deben usar Lync Web App 2013 para unirse a las reuniones de Lync Server 2013 hasta que sus clientes se actualicen. Tenga en cuenta que los usuarios de Office Communicator 2007 R2 pueden continuar usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero no son compatibles con las características de conferencia.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migrar usuarios en función de sus necesidades de conferencia

**Organizadores de reuniones frecuentes.**    Considere migrar con frecuencia los organizadores de reuniones al principio del proceso para poder aprovechar las nuevas características de lync Server 2013 y Lync 2013 descritas en [las nuevas características de conferencia de Lync Server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Usuarios de Live Meeting.**    Si va a migrar desde Office Communications Server 2007 R2 y tiene usuarios que necesitan características de conferencias web específicas de Live Meeting, especialmente en el caso de reuniones y salas de despiece de gran tamaño, tiene las siguientes opciones:

  - Aconseje a los organizadores que usen el servicio de Live Meeting, si está disponible en su organización.

  - Deje los organizadores alojados en la versión anterior de Office Communications Server para que puedan continuar con la programación de conferencias web de Live Meeting basadas en servidor.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migrar reuniones y contenido de reuniones existentes

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migrar reuniones desde Lync Server 2010

Al mover un usuario de Lync Server 2010 a Lync Server 2013, la siguiente información se mueve con la cuenta del usuario:

  - Reuniones ya programadas por el usuario. Esto incluye los directorios de conferencias y los datos de conferencia.

  - Número de identificación personal (PIN) del usuario. El PIN actual del usuario sigue funcionando hasta que venza o cuando el usuario solicite un nuevo PIN.

Sin embargo, la siguiente información de la cuenta de usuario no se mueve al nuevo servidor:

  - Contenido de la reunión, por ejemplo, presentaciones de PowerPoint, contenido de pizarra y datos de sondeos

Para mover el contenido que se ha compartido en las reuniones, use el parámetro MoveMeetingContent del cmdlet Move-CsUser. Para obtener más información sobre el uso de este cmdlet, consulte [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) en la documentación de cmdlets de Lync Server 2013.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migrar reuniones desde Office Communications Server 2007 R2

Las reuniones de Office Communications Server 2007 R2 son llamadas en conferencia (prefijos de dirección URL conf://) o conferencias web (prefijo meet://URL). Lync Server 2013 no admite estas conferencias de conf://y meet://anteriores, y no se migran junto con la cuenta de usuario. Después de la migración, debe indicar a los usuarios que actualicen los vínculos de las reuniones en línea que hayan programado. Pueden hacerlo después de instalar el cliente de Lync 2013 abriendo una invitación de reunión programada (que actualiza la dirección URL de la reunión) y reenviando la invitación a los participantes.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Experiencia del usuario durante la migración de Lync Server 2010

Esta sección proporciona un resumen de la experiencia de conferencia de los usuarios al migrar desde Lync 2010. Para obtener más información sobre cómo pueden coexistir los clientes de Lync Server 2013 e interactuar con versiones de cliente y servidor anteriores, consulte [interoperabilidad de cliente en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Unirse a reuniones de Lync Server 2010 con un cliente de Lync 2013

Durante la migración desde Lync Server 2010, es posible que haya un período de coexistencia cuando los usuarios se unan a reuniones de Lync Server 2010 con un cliente de Lync 2013. Estos usuarios tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:

  - En las opciones de administración de **participantes** , a las que se puede acceder seleccionando el icono de personas en la ventana de la reunión, la opción **sin mensajería instantánea** no funciona.

  - La vista de Galería no funciona en las videoconferencias. El usuario solo ve el orador activo en lugar de todos los altavoces. En la lista de opciones de **diseño** , la **vista de Galería** no está disponible

  - La lista de participantes se muestra de forma predeterminada en las videoconferencias.

  - Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear las imágenes destacadas** y **anclar a la Galería** no estarán disponibles.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Experiencia del usuario durante la migración de Office Communications Server 2007 R2

Esta sección proporciona un resumen de la experiencia de conferencia de los usuarios al migrar desde Office Communications Server 2007 R2, tanto antes como después de instalar Lync 2013. Para obtener más información sobre cómo pueden coexistir los clientes de Lync Server 2013 e interactuar con versiones de cliente y servidor anteriores, consulte [interoperabilidad de cliente en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Después de migrar la cuenta de usuario, antes de instalar Lync 2013

Después de que un usuario se migra al servidor de Lync Server 2013, pero antes de que se instalen nuevos clientes, los usuarios de Office Communicator 2007 R2 pueden continuar usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero las características de conferencia no se posible.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Después de migrar la cuenta de usuario, después de instalar Lync 2013

Cuando un usuario migrado instala Lync 2013, también se instala el complemento de reunión en línea para Lync 2013. Esto tiene los siguientes efectos:

  - Todas las reuniones programadas posteriormente usan el nuevo formato de reunión, que usa una dirección de https://en lugar de la dirección heredada de meet://Live Meeting.

  - En una implementación administrada por ti de Lync 2013, el administrador tiene la opción de desinstalar el complemento de conferencias para Microsoft Office Outlook, que se usa para programar Live Meeting Server y las reuniones basadas en servicios. Sin embargo, es posible que tenga usuarios que necesiten continuar programando reuniones de servicio de Live Meeting. En este caso, puede permitir que ambos complementos coexistan.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Reuniones con organizaciones federadas que usan clientes anteriores

Los usuarios de organizaciones federadas que usan Microsoft Office Communicator 2007 no pueden unirse a reuniones de Lync Server 2013 de su organización si dichas reuniones están bloqueadas por el organizador. Debe reprogramar estas reuniones en Lync Server 2013 de modo que cuando los participantes federados se unan a la reunión con la nueva dirección URL de la reunión de https://, pueden usar Lync Web App.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

