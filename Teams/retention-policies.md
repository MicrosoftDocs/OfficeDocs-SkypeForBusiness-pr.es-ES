---
title: Directivas de retención en Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: En este artículo, obtendrá información sobre las directivas de retención y sobre cómo crearlas y administrarlas en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3b7854af353b9619a1e668006c4e143ac8d37e77
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130661"
---
# <a name="retention-policies-in-microsoft-teams"></a>Directivas de retención en Microsoft Teams

Las directivas de retención permiten administrar de manera más efectiva la información en su organización. Use las directivas de retención para conservar datos que sean necesarios para cumplir con las directivas internas de la organización, las normas del sector o las necesidades jurídicas, así como para eliminar datos que se consideren una responsabilidad, que ya no se le exige que conserve, o no tiene un valor legal o comercial.

De forma predeterminada, los datos de chat, canal y archivos de los equipos se conservan indefinidamente, a menos que haya un intento de eliminar el contenido por medio de directivas de retención, eliminaciones de usuarios, eliminación de administradores, etc. Como administrador, puede configurar las directivas de retención de Teams para los mensajes instantáneos y de canal y decidir de forma proactiva Si desea conservar los datos, eliminarlos o conservarlos durante un período de tiempo específico y, a continuación, eliminarlos.

Cree y administre directivas de retención para equipos y otras cargas de trabajo en el [centro de cumplimiento de Microsoft 365](https://protection.office.com/) o mediante los cmdlets de PowerShell del centro de cumplimiento de & de seguridad. Puede aplicar una directiva de retención de Teams a toda la organización o a usuarios y equipos específicos.

> [!NOTE]
> Aún no se admite la configuración de retención de mensajes de canal privado. Se admite la retención de archivos compartidos en canales privados.

Para obtener más información sobre las directivas de retención para Microsoft 365 u Office 365, consulte [información general sobre las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="what-are-retention-policies-for-teams"></a>¿Qué son las directivas de retención de Teams?

Cuando configura una directiva de retención para Teams u otra carga de trabajo, puede configurarlos para:

- **Retener datos**: use una directiva de retención para asegurarse de que los datos sean retenidos durante un período de tiempo específico, independientemente de lo que suceda en la aplicación del usuario. Los datos se retienen por motivos de cumplimiento y están disponibles para eDiscovery hasta que concluya el período de retención, tras lo cual la directiva indica si debe eliminar los datos o hacer nada. Por ejemplo, si crea una directiva de retención de Teams para conservar los mensajes del canal durante 7 años, los mensajes se conservan para eDiscovery durante 7 años, incluso si los usuarios eliminan sus mensajes en Teams.
- **Eliminar datos**: use una directiva de retención para eliminar datos y asegurarse de que no es responsabilidad de su organización. Con una directiva de retención de Teams, al eliminar datos, se eliminan de forma permanente de todas las ubicaciones de almacenamiento en el servicio de Teams.

Con directivas de retención para Teams, puede:

- Retener mensajes de canal y/o chats de Teams durante un periodo determinado y, a continuación, hacer nada.
- Retener mensajes de canal y/o chats de Teams durante un periodo determinado y, a continuación, eliminar los datos.
- Eliminar mensajes de canal y/o chats de Teams después de un tiempo especificado.

> [!NOTE]
> Recuerde que en Teams, los archivos que los usuarios comparten en chats privados se almacenan en la cuenta de OneDrive para la Empresa del usuario que compartió el archivo. Y los archivos que los miembros del equipo cargan en una conversación de canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, para conservar o eliminar archivos en Teams, cree directivas de retención que se apliquen a OneDrive para la Empresa y SharePoint Online.

Cuando los datos están sujetos a una directiva de retención, los usuarios pueden continuar trabajando con ellos porque los datos se retienen en su ubicación original. Si un usuario edita o elimina datos que están sujetos a la directiva, se guarda una copia en una ubicación segura donde se conserva mientras la directiva está vigente.

La licencia, mínima requerida, para las directivas de retención es Office 365 E3. Para obtener más información sobre las licencias, vea [Descripción del servicio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-work"></a>Cómo funcionan las directivas de retención de Teams

Las conversaciones de Teams se almacenan en una carpeta oculta (Teamschat) en el buzón de cada usuario en el chat y los mensajes de canal de equipos se almacenan en una carpeta oculta (Teamschat) en el buzón de grupo de un equipo. Teams usa un servicio de chat con tecnología de Azure que también almacena estos datos. Además, este servicio almacena los datos indefinidamente de manera predeterminada. Con una directiva de retención de Teams, al eliminar datos, los datos se eliminan de forma permanente de los buzones de Exchange y del servicio de charla subyacente.

Al aplicar una directiva de **retención de** contenido a los chats de Teams o los mensajes de canal, esto es lo que sucede:

- Si un usuario modifica o elimina un mensaje de canal o de chat durante el período de retención, el mensaje se copia (si se ha editado) o se ha movido (si se ha eliminado) a la carpeta SubstrateHolds y se ha guardado allí hasta que vence el período de retención. Si la directiva está configurada para eliminar datos cuando expire el período de retención, los mensajes se eliminarán de forma permanente el día en que expire el período de retención.
- Si un usuario no elimina un mensaje de canal o de chat durante **el período de retención,** el mensaje se mueve a la carpeta SubstrateHolds en un día después de que venza el período de retención. Si la directiva está configurada para eliminar datos cuando concluya el período de retención, el mensaje se eliminará permanentemente un día después de que se mueva a la carpeta.

Al aplicar una directiva **de eliminación de retención** a los chats y los mensajes de canal de Teams, esto es lo que sucede:

- Cuando vence una conversación o un mensaje de canal, es decir, la antigüedad del mensaje es mayor de la permitida por **la Directiva de eliminación de retención** , un servicio back-end, identifica los mensajes expirados y comienza a eliminarlos en el almacenamiento de información back-end (buzón de usuario o de grupo).
- Una vez que se elimina un mensaje en el almacenamiento back-end, se desencadena un proceso para eliminar el mismo mensaje en el servicio de chat de Azure y la aplicación de Teams del usuario. Para que los mensajes se eliminen en la aplicación de Teams, la aplicación debe estar conectada a Internet y estar en estado de inactividad (sin actividad de usuario), de modo que el proceso de eliminación no interfiera en la experiencia del usuario. Puesto que un usuario puede tener varios dispositivos, que pueden estar en diferentes Estados, las eliminaciones de retención no se sincronizarán con esos dispositivos a la vez.
- Una vez completada la eliminación de mensajes en el almacenamiento de back-end, esos mensajes dejarán de mostrarse en los informes de búsqueda de cumplimiento, como eDiscovery.

> [!NOTE]
> El mismo flujo funciona para chats de interoperabilidad de Skype Empresarial Online y Teams. Cuando un chat de Skype Empresarial Online llega a Teams, se convierte en un mensaje en una conversación de chat de Teams y se ingiere en el buzón correspondiente. Las directivas de retención de Teams eliminarán estos mensajes de la conversación Teams. Sin embargo, si el historial de conversaciones está activado para Skype Empresarial Online y desde el lado del cliente de Skype Empresarial Online, estos se guardan en un buzón, los datos de este chat no son controlados por una directiva de retención de Teams.

> [!NOTE]
> La eliminación de mensajes es permanente e irreversible.

Las directivas de retención de Teams se basan en la fecha en que se crearon los mensajes de canal o chats, y son retroactivas Es decir, si crea una directiva de retención para eliminar datos anteriores a 90 días, los datos de Teams creados hace más de 90 días se eliminan.

Es posible que una directiva de retención que se aplique a SharePoint Online o OneDrive para la Empresa pueda eliminar un archivo al que se hace referencia en un mensaje de canal o chat de Teams antes de que se eliminen esos mensajes. En este escenario, el archivo seguirá apareciendo en el mensaje de Teams, pero, cuando los usuarios hagan clic en el archivo, se mostrará el error "no se encuentra el archivo". Esto también puede ocurrir en ausencia de una directiva, si alguien elimina manualmente un archivo de SharePoint Online o de OneDrive para la Empresa.

### <a name="considerations-and-limitations"></a>Consideraciones y limitaciones

Estas son algunas consideraciones y limitaciones que debe tener en cuenta al trabajar con directivas de retención de Teams:

- Teams requiere una directiva de retención que es independiente de otras cargas de trabajo. En otras palabras, debe crear políticas de retención específicas para los mensajes de canal y/o chats de Teams. Por este motivo, no puede incluir Teams en directivas de retención para toda la organización.

- No se admiten mensajes de canal privado. En este momento, las directivas de retención creadas para Teams no se aplican a los mensajes de canal privado.

- Teams no es compatibles con la configuración avanzada de retención, como la posibilidad de aplicar una directiva al contenido que contiene palabras clave o información confidencial. Actualmente, las directivas de retención de Teams se aplican a todo el contenido de mensajes de canal y/o chat.

- Una directiva de retención de equipos desencadenará un proceso para eliminar mensajes de chat y de canal cuando esos mensajes expiren (según la fecha de creación del mensaje). Sin embargo, en función de la carga del servicio, puede tardar hasta siete días en eliminar de forma permanente estos mensajes de almacenamiento de back-end y de la aplicación de Teams. Además, estos mensajes se pueden buscar con las herramientas de cumplimiento (eDiscovery, la búsqueda de usuarios finales) hasta que se eliminen permanentemente del almacenamiento de información de back-end.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>Múltiples directivas de retención y los principios de la retención

Si configura varias directivas de retención de Teams con distintas duraciones, se aplicarán [los principios de la retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence). A continuación, encontrará información general de lo que tiene prioridad:

- La preservación tiene prioridad sobre la eliminación
- El período más largo de preservación siempre tiene prioridad
- La inclusión explícita tiene prioridad sobre la inclusión implícita en lo que respecta a ubicaciones.
- El período de eliminación más corto tiene prioridad

## <a name="when-to-use-retention-policies-for-teams"></a>Cuándo usar directivas de retención para Teams

En muchos casos, las organizaciones consideran que los datos de chat privados son más una responsabilidad que los mensajes de canal, que generalmente son conversaciones más relacionadas con el proyecto.

Puede establecer directivas de retención distintas para chats privados (1 a 1 o 1 a muchos chats) y mensajes de canal. También puede configurar directivas únicas para aplicarlas a determinados usuarios o equipos de la organización. En el caso de chats de Teams, puede seleccionar a qué usuarios aplicar la directiva. En el caso de los mensajes de canal de Teams, puede seleccionar a qué equipos aplicar la directiva.

Por ejemplo, en el caso de los mensajes del canal, puede aplicar una directiva de eliminación de un año a equipos específicos de su organización y aplicar una directiva de eliminación de tres años a todos los demás equipos.

## <a name="manage-retention-policies-for-teams"></a>Administrar directivas de retención para Teams

### <a name="using-the-security--compliance-center"></a>Usar el Centro de seguridad y cumplimiento

#### <a name="create-a-retention-policy"></a>Crear una directiva de retención

Para crear una directiva de retención para los mensajes de canal y chats de Teams, haga lo siguiente:

1. En el panel izquierdo del Centro de seguridad y cumplimiento, vaya a **Control de la información** > **Retención**.
2. Seleccione **Crear**.
3. En la página **Asignar un nombre a la directiva**, escriba un nombre y una descripción para la directiva y, a continuación, haga clic en **siguiente**.
4. En la página **Configuración**, especifique si desea conservar los datos, eliminarlos, o ambos, el período de retención y, a continuación, haga clic en **siguiente**.
5. En la página **Elegir ubicaciones**, siga este procedimiento y, a continuación, haga clic en **siguiente**:

    - Para aplicar la directiva a los mensajes del canal, active **Mensajes de canal de Teams**.  Si desea aplicar la directiva a equipos específicos en su organización, seleccione **Elegir equipos** y, a continuación, seleccione los equipos que desee.
    - Para aplicar la directiva a los chats, active **Chats de Teams**. Si desea aplicar la directiva a usuarios específicos en su organización, seleccione **Elegir usuarios** y, a continuación, seleccione los usuarios que desee.
      > [!NOTE]
      > Al activar **Mensajes de canal de Teams** y/o **Chats de Teams**, el resto de las ubicaciones se desactivan automáticamente. Una directiva de retención de Teams solo puede incluir ubicaciones de Teams.

        ![Captura de pantalla de las opciones de mensajes del canal de Teams y chats de Teams en la página elegir ubicaciones](media/retention-policies-create.png)

      > [!IMPORTANT]
      > Los chats de equipos y los mensajes de canal no se ven afectados por las directivas de retención aplicadas a buzones de usuario o grupo en las ubicaciones de **correo electrónico de Exchange** o de **grupos de Microsoft 365** . A pesar de que los mensajes de canal y chats de Teams se almacenan en Exchange, solo se verán afectados por una directiva de retención que se aplique a la ubicación de Teams.

6. Revise la configuración y, después, cuando esté listo, seleccione **crear esta directiva**.

#### <a name="edit-a-retention-policy"></a>Editar una directiva de retención

Para editar una directiva de retención de Teams, haga lo siguiente:

1. En el panel izquierdo del Centro de seguridad y cumplimiento, vaya a **Control de la información** > **Retención**.
2. En la lista de directivas de retención, seleccione la casilla situada junto a la directiva de retención que quiere editar.
3. Seleccione **editar** junto a lo que desea editar, realice los cambios que desee, haga clic en **guardar** y, a continuación, haga clic en **cerrar**.

    ![Captura de pantalla de las opciones de mensajes del canal de Teams y chats de Teams en la página elegir ubicaciones](media/retention-policies-edit.png)

> [!WARNING]
> Si ha configurado equipos específicos o usuarios específicos para que se incluyan para los mensajes de canal de Teams o los chats de Teams, y los modifica para quitar el último de la ubicación, la configuración de esa ubicación se revierte a **todos**. Asegúrese de que esta es la configuración que desea antes de guardar la Directiva.
> 
> Por ejemplo, si ha especificado un usuario de la conversación de equipos para incluir en su Directiva de retención que está configurada para eliminar datos y, a continuación, modifica la Directiva para quitar a este usuario, todos los usuarios estarán sujetos a la Directiva de retención que elimina de forma permanente los mensajes de chat de sus equipos. Lo mismo se aplica a las inclusiones de los mensajes de canal de Teams.
> 
> En este escenario, alterne la ubicación si no quiere que la configuración **todo** para los mensajes de canal de equipos o los mensajes de chats de Teams estén sujetas a la Directiva de retención. También puede especificar que no se excluya de la Directiva.


#### <a name="delete-a-retention-policy"></a>Eliminar una directiva de retención

Para eliminar una directiva de retención de Teams, haga lo siguiente:

1. En el panel izquierdo del Centro de seguridad y cumplimiento, vaya a **Control de la información** > **Retención**.
2. En la lista de directivas de retención, seleccione la casilla de verificación junto a la directiva de retención que desea eliminar.
3. Seleccione **Eliminar directiva**.

### <a name="end-user-experience"></a>Experiencia de usuario final

En el caso de chats privados (chats de 1:1) o chats grupales, los usuarios finales verán que se eliminan las conversaciones anteriores a la configuración de la Directiva de retención y se muestra un mensaje de control que indica "hemos eliminado mensajes anteriores debido a la Directiva de retención de su organización", además de los mensajes no eliminados.
:::image type="content" source="media/retention-policies-image1.png" alt-text="Captura de pantalla de la retención de chat":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Captura de pantalla de la retención de conversaciones grupales":::

Para los mensajes de canal, los usuarios finales (miembros del canal) verán que los mensajes eliminados desaparecen de la vista después de que los mensajes expiren. Si el mensaje eliminado era un mensaje principal de una conversación encadenada, se mostrará un mensaje que indicará que se ha eliminado este mensaje debido a una directiva de retención.

:::image type="content" source="media/retention-policies-image3.png" alt-text="Captura de pantalla de canal antes de la retención":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Captura de pantalla del canal después de la retención":::

> [!NOTE]
> La mensajería de usuario final no se pueden modificar en este momento.


### <a name="using-powershell"></a>Con PowerShell

Para crear y administrar directivas de retención de Teams mediante [PowerShell del centro de cumplimiento de seguridad &](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell), use los siguientes cmdlets:

|Directiva|Regla|
|---|---|
|[Nuevo: RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [Nuevo: RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>Problemas conocidos

Los siguientes son problemas conocidos para las directivas de retención en Teams a los que se les está dando seguimiento e investigando.

- En **elegir equipos** en la fila ubicaciones de **los mensajes del canal de Teams** , es posible que vea grupos de Microsoft 365 que no son también equipos. Este problema se corregirá en una actualización futura.

- En **Elegir usuarios** en la fila de ubicación de **Chats de Teams**, es posible que vea invitados y usuarios que no son buzones. Las directivas de retención no están pensadas para ser establecidas para invitados y estamos trabajando para quitarlas de la lista.

- Los trabajos de procesamiento de retención se ejecutan diariamente, pero se sabe que la latencia se ejecutó hasta 7 días, en algunos casos. Como resultado, es posible que, si tiene una directiva de retención de Teams para eliminar elementos anteriores a 60 días, estos elementos se puedan guardar hasta 67 días. Esto no es una nueva situación: sigue el modelo de Exchange. Por supuesto, en la mayoría de los casos, no hay ningún retraso.

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
