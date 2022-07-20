---
title: Administrar Q&A en reuniones de Teams
author: wlibebe
ms.author: wlibebe
ms.reviewer: sameer.sitaram
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
description: Obtenga información sobre cómo los administradores de TI pueden configurar, usar y administrar Q&A en Teams Q&A para un enfoque estructurado para recopilar preguntas, organizar discusiones, eliminar mensajes individuales, usar idiomas disponibles y comprender el ciclo de vida de los datos, así como las directivas de retención y eliminación de datos.
ms.openlocfilehash: 3ffdc4f48c43bef2d1d342983a63612c91bc40a9
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880434"
---
# <a name="manage-qa-in-teams-meetings"></a>Administrar Q&A en reuniones de Teams

Q&A permite a los moderadores tomar preguntas de los asistentes y responderlas en tiempo real. Esta característica es más adecuada para reuniones grandes y estructuradas, como ayuntamientos, seminarios web, todas las manos y entrenamientos.

En este artículo se describe cómo administrar Q&A y las directivas a nivel de usuario, que dictan si un organizador puede habilitar la&A de Teams en sus reuniones.

## <a name="prerequisites"></a>Requisitos previos

- Compruebe que no ha bloqueado el acceso a las [direcciones IP y URL de Yammer.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- Para permitir a los usuarios de su organización agregar Q&A a las reuniones de Teams, debe confirmar que los inicios de sesión del servicio Office 365 Yammer están habilitados en Azure Active Directory. Siga los pasos siguientes para confirmar que los inicios de sesión están habilitados:
  - Vaya al Centro  >  de **administración de Azure AD****Todas las** > **aplicaciones** >  empresariales Office 365 **Propiedades** **de Yammer** > .
  - Para la opción **¿Está habilitado para que los usuarios inicien sesión?** , seleccione **Sí** si es necesario.

## <a name="who-can-use-qa"></a>Quién puede usar Q&A

Los siguientes tipos de usuario pueden usar Q&A:

- Usuario normal: un usuario con credenciales de Microsoft 365 en su inquilino.
- Usuario federado: un usuario con credenciales de Microsoft 365 para un inquilino diferente.
- Usuario invitado: cualquier invitado que agregue a Microsoft Teams, SharePoint o Azure Active Directory.

> [!NOTE]
> Q&A no estará disponible para Ver solo los asistentes que se unan más allá de la capacidad de la reunión.

Cuando los administradores habilitan Q&A, los usuarios con el [rol de organizador](https://aka.ms/GetQnA) pueden activar Q&A al crear o actualizar reuniones. A través de las opciones de reunión de Teams y Outlook, los organizadores también pueden quitar Q&A de las reuniones en las que se agregó anteriormente para evitar que los asistentes usen la característica.

## <a name="use-the-teams-admin-center-to-manage-qa"></a>Usar el Centro de administración de Teams para administrar Q&A

Es posible que su organización tenga requisitos para limitar qué organizadores pueden activar Q&A. Puede usar el Centro de administración de Teams para administrar qué organizadores pueden activar Q&A en reuniones grandes.
Siga estos pasos para controlar qué organizadores pueden usar Q&A:

1. En el Centro de administración de Teams, vaya a **Directivas** > [**de reunión de**](/meeting-policies-participants-and-guests) reuniones
2. Seleccione una directiva existente o cree una nueva y asígnele un nombre como "No Q&A para estos organizadores"
3. Desplácese hasta la sección denominada **"Participantes & invitados"**, seleccione Deshabilitar para la configuración **"Experiencia de respuesta & preguntas"** y guarde la directiva.
4. Asigne la directiva a grupos de M365, usuarios finales o suscripciones específicas que quiera impedir que configureN Q&A

## <a name="use-powershell-to-manage-qa"></a>Usar PowerShell para administrar Q&A

Es posible que su organización tenga requisitos para limitar qué organizadores pueden activar Q&A. Puede usar PowerShell para administrar qué organizadores pueden activar Q&A en reuniones grandes.

Comando de PowerShell de ejemplo para habilitar Q&A:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>Eliminar un mensaje individual de Q&A en Teams

Para eliminar una pregunta o respuesta publicada en la aplicación Q&A, siga estos pasos:

1. Inicie sesión en el Centro de Administración de Exchange como administrador global.
2. Vaya a **Buzones** de **los destinatarios** >  y busque por nombre el usuario que organizó la reunión.
3. Seleccione el organizador de la reunión y haga clic en **Administrar delegación de buzones**. En la sección **Leer y administrar** , seleccione **Editar** > **agregar permisos**.
4. Agréguese como delegado del organizador de la reunión y seleccione Guardar.
5. Abre Calendario de Outlook en la Outlook Web App (no el escritorio) y selecciona **Agregar calendario** y, a continuación, **Agregar desde el directorio**.
6. Busque el organizador de la reunión y agregue su calendario a **Mis calendarios**. Las reuniones del usuario seleccionado se mostrarán ahora en el calendario.
7. En el calendario, busque la reunión para la que desea eliminar contenido, abra el registro de la reunión y seleccione **Chatear con participantes**. Al seleccionar el chat con los participantes, se abrirá el chat de la reunión en Teams.
8. Vaya a la aplicación Q&A en la barra de aplicaciones de Teams.
9. Busque las preguntas o respuestas que quiera eliminar y seleccione Eliminar.
10. Cuando haya terminado de eliminar contenido, vuelva al Centro de Administración de Exchange y quítese a sí mismo como delegado del organizador de la reunión.

> [!NOTE]
> Si elimina una pregunta antes de eliminar las respuestas, la primera respuesta a la pregunta se convertirá en la pregunta.
>
> Para evitar esto, siga estos pasos en orden:
>
> 1. Identificar la pregunta que desea eliminar
> 2. Eliminar las respuestas a la pregunta
> 3. Eliminar la pregunta

## <a name="available-languages-for-yammer-versus-teams"></a>Idiomas disponibles para Yammer frente a Teams

La Q&A se aplicará de forma predeterminada al idioma del usuario de Teams. Cuando haya una diferencia en los idiomas disponibles para Teams frente a Yammer, se producirán los siguientes valores predeterminados de idioma:

- Idioma principal más cercano: Yammer usará de forma predeterminada el idioma principal más cercano, si está disponible. Por ejemplo, Yammer no proporciona una versión francesa canadiense (fr-CA), por lo que mostrará contenido en francés (fr-FR) en su lugar.
- Idioma no compatible: si yammer no proporciona el idioma, Yammer usará de forma predeterminada el inglés de Ee. UU. (es-ES).

## <a name="ediscovery"></a>eDiscovery

eDiscovery para Q&A funcionará igual que eDiscovery para cualquier otro contenido de Yammer.

- Si usa Teams Q&A en la aplicación de Teams de su inquilino, este contenido estará disponible en eDiscovery independientemente de la configuración o la existencia de su red de Yammer. Para usar eDiscovery para contenido estándar de Yammer, su red de Yammer debe estar en [modo nativo](/yammer/configure-your-yammer-network/overview-native-mode).
- Al realizar eDiscovery, puede determinar si los mensajes se generaron en Yammer o a través de Q&A en Teams. En la sección Metadatos de archivo, encontrará esa información en el campo Clase de elemento.
- Si su organización usa la&A de Q de Teams, con tecnología de Yammer, el contenido generado por Q&A se considera contenido de Yammer y será reconocible. Para obtener más información sobre eDiscovery en aplicaciones de Microsoft 365, vea [Soluciones de exhibición de documentos electrónicos en Microsoft 365.](/microsoft-365/compliance/ediscovery)
- Si el organizador de la reunión habilita la publicación anónima, las preguntas que publiquen los asistentes se darán a conocer en el buzón del organizador para la exhibición de documentos electrónicos.

## <a name="data-storage"></a>Almacenamiento de datos

Q&Los mensajes creados como parte de la reunión se almacenan como mensajes de Yammer. Estos mensajes se almacenan en Yammer y se ingiere para eDiscovery.
Los archivos siempre se almacenan en SharePoint, que controla todas las directivas y ubicaciones del resto de datos.

Las siguientes instrucciones explican cómo se almacenan los datos de mensajería:

- Q&Un contenido se puede buscar a través de eDiscovery y Advanced eDiscovery en el nivel de usuario.
- Los datos de los mensajes (que incluyen el contenido del mensaje) se almacenarán en Norteamérica o en la UE de forma predeterminada (en función de la ubicación de red de Yammer del cliente).
- Para los inquilinos que no tengan una red de Yammer existente, la red de Q&A Yammer se creará en la región de Yammer Estados Unidos. Los mensajes de la organización de Q&A siempre se almacenarán en estados Unidos.
- De forma similar a las pestañas de OneNote, al quitar Q&A de una reunión, no se eliminan los datos de la reunión. Al quitar Q&A de la reunión, solo se quita el acceso a los datos de la reunión. Si vuelve a agregar la pestaña Q&A, volverá a ver todas las conversaciones de la reunión.

## <a name="gdpr-for-qa-in-teams"></a>RGPD para Q&A en Teams

Al completar una solicitud del interesado a través del Centro de Administración de Microsoft 365, esta elimina automáticamente la información de contacto de los usuarios de todo su contenido en la Q&A.

## <a name="data-lifecycle-for-qa-in-teams"></a>Ciclo de vida de datos de Q&A en Teams

El ciclo de vida de los datos generados por Q&A en Teams depende de la configuración de retención de datos de Yammer del Centro de cumplimiento. Si elimina con fuerza todos los usuarios de la reunión que recibieron una copia de los mensajes de Q&A en su partición del sustrato a través de Azure Active Directory, Yammer eliminará su copia del contenido de Q&A para esa reunión en un plazo de 30 días a partir de la eliminación del usuario.

## <a name="retention-and-deletion"></a>Retención y eliminación

La retención de contenido sigue las directivas de retención establecidas para Yammer, independientemente de si tiene diferentes directivas establecidas para Yammer y Teams.

> [!NOTE]
> Si su red de Yammer no está en modo nativo, las directivas creadas aquí se aplicarán solo a los datos de La&A de Teams. En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (Azure AD), todos los grupos son grupos de Microsoft 365 y todos los archivos se almacenan en SharePoint Online.

## <a name="faq"></a>Preguntas más frecuentes

**P: Cómo exportar contenido de Q&A?**

**Un:** El contenido de Q&A se almacena en la Centro de cumplimiento de Microsoft 365 y se obtiene acceso a él a través de eDiscovery. Las iteraciones futuras incluirán un informe de resaltado de la reunión y la funcionalidad de exportación para los organizadores de la reunión.

**P: ¿Q&A admite las funcionalidades multigerea de Microsoft 365?**

**Un:** Q&A no es compatible actualmente con las funcionalidades multi geo de Microsoft 365. Q&Los datos A se almacenarán en Norteamérica o en la UE de forma predeterminada (en función de la ubicación de red de Yammer del cliente).

**P: ¿Dónde puedo obtener más información sobre las reuniones estructuradas?**

**Un:** Siga estos [procedimientos recomendados](/MicrosoftTeams/quick-start-meetings-live-events) para hospedar reuniones grandes con éxito en Microsoft Teams.

**P: ¿Cuál es la diferencia entre configurar Q&A a través de la Tienda de aplicaciones de Teams y usar Las opciones de reunión?**

**Un:** Hemos simplificado la habilitación de Q&A a Las opciones de reunión.A partir de agosto de 2022, la aplicación Q&A de la tienda de aplicaciones de Teams ya no se admitirá, por lo que Q&A solo debe habilitarse a través de Opciones de reunión. Si es el organizador de las reuniones en las que Q&A se habilitó a través de la tienda de aplicaciones de Teams, quite la aplicación Q&A y, en su lugar, solo habilite a través de Opciones de reunión.

**P: ¿Por qué veo dos iconos de Q&A en mi reunión?**

**Un:** Está viendo dos iconos de Q&A en la reunión porque Q&A también se ha habilitado a través de Opciones de reunión. Quite la aplicación Q&A que se agregó a través de teams App Store siguiendo las instrucciones que se indican a continuación. Haga esto para todas las reuniones en las que previamente había agregado Q&A a través de la tienda de aplicaciones de Teams.

**Cómo quitar la aplicación Q&A que se agregó desde la tienda de aplicaciones de Teams.**

1. En La versión de escritorio de Teams, únase a la reunión en la que agregó Q&A anteriormente.

2. En el panel superior, seleccione la segunda aparición del icono Q&A en la ventana Reunión de Teams: esta es la experiencia de Q&A que se agregó a través de la App Store de Teams.

3. Con la pestaña Q&A seleccionada abierta, haga clic en los puntos suspensivos y haga clic en "Quitar". Esto quitará la experiencia de Q&A que se agregó a través de la tienda de aplicaciones de Teams.

4. Haga clic en "Quitar" para quitar permanentemente la experiencia de Q&A que se agregó a través de la tienda de aplicaciones de Teams.

> [!NOTE]
> Solo la aplicación Q&A agregada a través de la tienda de aplicaciones de Teams tendrá puntos suspensivos para quitar la aplicación Q&A. La experiencia Q&A habilitada a través de Opciones de reunión no tendrá puntos suspensivos y no se puede quitar desde aquí.

¡Eso es todo! Ahora solo hay una experiencia Q&A, con tecnología de Opciones de reunión. Se quitará la aplicación Q&A agregada a través de la tienda de aplicaciones de Teams.
