---
title: 'Lync Server 2013: consideraciones de migración para las reuniones'
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
ms.openlocfilehash: 48ee24dca1cdf083de990ef42dae4017ed927e15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524567"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Consideraciones sobre la migración para las reuniones en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-10_

En esta sección se describen los temas siguientes:

  - Cambios en las reuniones en Microsoft Lync Server 2013

  - Migrar usuarios según sus necesidades de conferencia

  - Migrar reuniones existentes y contenidos de reuniones

  - Experiencia del usuario durante la migración de Lync Server 2010

  - Experiencia del usuario durante la migración de Office Communications Server 2007 R2

  - Compatibilidad de Microsoft Lync 2013 con reuniones en versiones anteriores del servidor

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Cambios en las reuniones en Lync Server 2013

**Características de Lync Server 2013.**     Lync Server 2013 proporciona nuevas características de conferencia que se ponen a disposición de los usuarios después de que sus cuentas se muevan a Lync Server 2013 y inician sesión con el cliente de Lync 2013. Las nuevas características se describen en [nuevas características de conferencia en Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Dirección URL de la reunión.**     Al igual que en Lync Server 2010, todas las reuniones recientemente programadas en Lync Server 2013 tienen un prefijo de dirección URL de https://y las reuniones existentes se migran junto con las cuentas de usuario. Sin embargo, Lync Server 2013 no admite la llamada de conferencia de Office Communications Server 2007 R2 (Prefijo de dirección URL de conf://) ni la conferencia web (Prefijo de dirección URL meet://). Para obtener más información, vea "migrar reuniones de Office Communications Server 2007 R2" más adelante en este tema.

**Compatibilidad con clientes.**     A diferencia de Lync Server 2010, Lync Server 2013 no es compatible con los clientes de Office Communicator para conferencias. No puede usar los siguientes clientes para unirse a reuniones programadas mediante el complemento de reunión en línea para Lync 2013:

  - Office Communicator 2007 R2

  - Operador de Microsoft Office Communications Server 2007 R2

  - Office Communicator 2007

  - Office Live Meeting 2007

Durante la migración, los usuarios de Office Communicator 2007 R2 deben usar Lync Web App 2013 para unirse a las reuniones de Lync Server 2013 hasta que se actualicen sus clientes. Tenga en cuenta que los usuarios de 2007 R2 de Office Communicator pueden seguir usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero no se admiten las características de conferencia.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migrar usuarios según sus necesidades de conferencia

**Organizadores de reuniones frecuentes.**     Considere la posibilidad de migrar los organizadores de reuniones frecuentes al principio del proceso para que puedan aprovechar las nuevas características de Lync Server 2013 y Lync 2013 descritas en [nuevas características de conferencia en Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Usuarios de Live Meeting.**     Si va a migrar desde Office Communications Server 2007 R2 y tiene usuarios que necesitan características de conferencia Web específicas para Live Meeting (en particular, para reuniones de gran tamaño y salas de salida), tiene las siguientes opciones:

  - Aconseje a los organizadores que usen el servicio de Live Meeting, en caso de que esté disponible en su organización.

  - Deje los organizadores hospedados en la versión anterior de Office Communications Server, para que puedan seguir programando conferencias web de Live Meeting basadas en servidor.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migrar reuniones existentes y contenidos de reuniones

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migrar reuniones desde Lync Server 2010

Cuando mueve un usuario de Lync Server 2010 a Lync Server 2013, la siguiente información se mueve con la cuenta del usuario:

  - Las reuniones ya programadas por el usuario. Esto incluye los directorios de conferencias y los datos de conferencia.

  - El número de identificación personal (PIN) del usuario. El PIN actual del usuario seguirá funcionando hasta que caduque o hasta que el usuario solicite un PIN nuevo.

Sin embargo, la siguiente información de la cuenta de usuario no se mueve al nuevo servidor:

  - Contenido de la reunión, por ejemplo, presentaciones de PowerPoint, contenido de la pizarra y datos de sondeo

Para mover el contenido que se ha compartido en las reuniones, use el parámetro MoveMeetingContent del cmdlet Move-CsUser. Para obtener más información sobre el uso de este cmdlet, consulte [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) en la documentación de cmdlets de Lync Server 2013.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migrar reuniones desde Office Communications Server 2007 R2

Las reuniones de Office Communications Server 2007 R2 son llamadas de conferencia (prefijos de dirección URL de conf://) o conferencias web (Prefijo de dirección URL de meet://). Lync Server 2013 no es compatible con estas conferencias anteriores de conf://y meet://, y no se migran junto con la cuenta de usuario. Después de la migración, debe indicar a los usuarios que actualicen los vínculos de las reuniones en línea que hayan programado. Pueden hacerlo después de instalar el cliente Lync 2013 abriendo una invitación de reunión programada (que actualiza la dirección URL de la reunión) y reenviando la invitación a los participantes.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Experiencia del usuario durante la migración de Lync Server 2010

En esta sección se proporciona un resumen de la experiencia de conferencia de los usuarios al migrar desde Lync 2010. Para obtener más información sobre cómo pueden coexistir los clientes de Lync Server 2013 e interactuar con versiones de cliente y servidor anteriores, vea [interoperabilidad de cliente en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Unirse a reuniones de Lync Server 2010 con un cliente de Lync 2013

Durante la migración desde Lync Server 2010, puede haber un período de coexistencia cuando los usuarios se unen a reuniones de Lync Server 2010 con un cliente de Lync 2013. Estos usuarios tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:

  - En las opciones de administración de **participantes** , a las que se puede tener acceso seleccionando el icono de personas en la ventana de la reunión, la opción de **mensajería instantánea sin reunión** no funciona.

  - La vista de Galería no funciona en las videoconferencias. El usuario solo ve el participante activo en lugar de todos los altavoces. En la lista de opciones de **selección de un diseño** , la **vista de Galería** no está disponible

  - La lista de participantes se muestra de forma predeterminada en las videoconferencias.

  - Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear la luz de vídeo** y **anclar al** participante de la galería no están disponibles.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Experiencia del usuario durante la migración de Office Communications Server 2007 R2

En esta sección se proporciona un resumen de la experiencia de conferencia de los usuarios al realizar la migración desde Office Communications Server 2007 R2, tanto antes como después de instalar Lync 2013. Para obtener más información sobre cómo pueden coexistir los clientes de Lync Server 2013 e interactuar con versiones de cliente y servidor anteriores, vea [interoperabilidad de cliente en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Después de migrar la cuenta de usuario, antes de instalar Lync 2013

Una vez que un usuario se migra al servidor de Lync Server 2013, pero antes de que se instalen nuevos clientes, los usuarios de Office Communicator 2007 R2 pueden seguir usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero no se admiten las características de conferencia.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Después de migrar la cuenta de usuario, después de instalar Lync 2013

Cuando un usuario migrado instala Lync 2013, también se instala el complemento de reunión en línea para Lync 2013. Esto tiene las siguientes repercusiones:

  - Todas las reuniones programadas posteriormente usarán el formato nuevo de reunión, que utiliza una dirección https:// en lugar de la dirección heredada de Live Meeting meet://.

  - En una implementación administrada de TI de Lync 2013, el administrador tiene la opción de desinstalar el complemento de conferencia para Microsoft Office Outlook, que se usa para programar las reuniones basadas en servicios y el servidor de Live Meeting. Sin embargo, puede tener usuarios que necesiten seguir programando reuniones del servicio de Live Meeting. En este caso, puede permitir que los dos complementos coexistan.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Reuniones con organizaciones federadas que usen clientes anteriores

Los usuarios de organizaciones federadas que usen Microsoft Office Communicator 2007 no pueden unirse a reuniones de Lync Server 2013 en su organización si esas reuniones están bloqueadas por el organizador. Debe reprogramar estas reuniones en Lync Server 2013 de modo que, cuando los participantes federados se unan a la reunión con la nueva dirección URL de reunión de https://, puedan usar Lync Web App.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

