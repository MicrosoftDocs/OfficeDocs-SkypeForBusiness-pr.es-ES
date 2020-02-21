---
title: Directivas de retención en Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Obtenga información sobre las directivas de retención y sobre cómo crearlas y administrarlas en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86cbb37b46bca606e7225ce0267a49c709fc9619
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160754"
---
# <a name="retention-policies-in-microsoft-teams"></a>Directivas de retención en Microsoft Teams

Las directivas de retención le ayudan a administrar de forma más eficaz la información de su organización. Use directivas de retención para mantener los datos necesarios para cumplir con las políticas internas de su organización, las regulaciones de la industria o las necesidades legales, y para eliminar datos que se consideren responsabilidad, que usted ya no necesita mantener o que no tiene ningún valor legal o para el negocio.

De forma predeterminada, los datos de chat, canal y archivos de Teams se conservan para siempre. Como administrador, puede configurar las directivas de retención de Teams para los mensajes instantáneos y de canal y decidir de forma proactiva Si desea conservar los datos, eliminarlos o conservarlos durante un período de tiempo específico y, a continuación, eliminarlos.

Cree y administre directivas de retención para equipos y otras cargas de trabajo en el [centro de cumplimiento de & de seguridad de Office 365](https://protection.office.com/) o mediante los cmdlets de PowerShell del centro de cumplimiento de & de seguridad. Puede aplicar una directiva de retención de un equipo a toda la organización o a determinados usuarios y equipos.

> [!NOTE]
> Aún no se admite la configuración de retención de mensajes de canal privado. La retención de archivos compartidos en canales privados es compatible.

Para obtener más información sobre las directivas de retención de Office 365, consulte [información general sobre las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="what-are-retention-policies-for-teams"></a>¿Qué son las directivas de retención de Teams?

Al configurar una directiva de retención para Teams o cualquier otra carga de trabajo, puede configurarla de la siguiente forma:

- **Retener datos**: Use una directiva de retención para asegurarse de que los datos se conservan durante un período de tiempo específico, independientemente de lo que suceda en la aplicación de usuario. Los datos se conservan por razones de cumplimiento y está disponible para eDiscovery hasta que vence el período de retención, después del cual la Directiva indica si no hace nada o elimina los datos. Por ejemplo, si crea una directiva de retención de Teams para conservar los mensajes de los canales durante 7 años, los mensajes se conservarán para eDiscovery durante 7 años, incluso si los usuarios eliminan sus mensajes en Teams.
- **Eliminar datos**: Use una directiva de retención para eliminar datos y asegurarse de que no es responsabilidad de su organización. Con una directiva de retención de Teams, al eliminar datos, se eliminan permanentemente de todas las ubicaciones de almacenamiento en el servicio de Teams.

Con las directivas de retención de Teams, puede hacer lo siguiente:

- Conserve los chats de los equipos y/o los mensajes de canal durante un tiempo específico y, a continuación, no haga nada.
- Retenga los chats de Teams y/o los mensajes de canal durante un tiempo específico y, a continuación, elimine los datos.
- Eliminar chats de equipos o mensajes de canal después de un tiempo determinado.

> [!NOTE]
> Recuerde que en Teams, los archivos que los usuarios comparten en las conversaciones privadas se almacenan en la cuenta de OneDrive para la empresa del usuario que compartió el archivo. Además, los archivos que los miembros del equipo se cargan en una conversación de canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, para conservar o eliminar archivos en Teams, cree directivas de retención que se apliquen a OneDrive para la empresa y SharePoint Online.

Cuando los datos están sujetos a una directiva de retención, los usuarios pueden seguir trabajando con él porque los datos se conservan en su ubicación original. Si un usuario modifica o elimina datos que están sujetos a la Directiva, se guarda una copia en una ubicación segura donde se conserva mientras la Directiva está activa.

El requisito mínimo de licencias para las directivas de retención es Office 365 E3. Para obtener más información sobre las licencias, consulte [licencias de Office 365 para Teams](Office-365-licensing.md).

## <a name="how-teams-retention-policies-work"></a>Funcionamiento de las directivas de retención de Teams

Los chats de equipos se almacenan en una carpeta SubstrateHolds oculta en el buzón de cada usuario en el chat y los mensajes de canal de Teams se almacenan en una carpeta SubstratesHolds oculta del buzón de grupo de un equipo. Teams usa un servicio de chat de Azure que también almacena estos datos y, de forma predeterminada, los almacenan los datos para siempre. Con una directiva de retención de Teams, al eliminar datos, los datos se eliminan de forma permanente tanto de los buzones de Exchange como del servicio de chat subyacente.

Al aplicar una directiva de retención a los chats y los mensajes de canal de Teams, esto es lo que sucede:

- Si un usuario modifica o elimina un mensaje de canal o de chat durante el período de retención, el mensaje se copia (si se ha editado) o se ha movido (si se ha eliminado) a la carpeta SubstrateHolds y se ha guardado allí hasta que vence el período de retención. Si la Directiva está configurada para eliminar datos cuando vence el período de retención, los mensajes se eliminan permanentemente el día en que vence el período de retención.
- Si un usuario no elimina un mensaje de canal o de chat durante el período de retención, el mensaje se mueve a la carpeta SubstrateHolds en un día después de que venza el período de retención. Si la Directiva está configurada para eliminar datos cuando se agote el período de retención, el mensaje se eliminará permanentemente un día después de que se mueva a la carpeta.

> [!NOTE]
> El mismo flujo funciona con los chats de Skype empresarial online y Teams. Cuando un chat de Skype empresarial online llega a Teams, se convierte en un mensaje en un chat de equipo y se infiere en el buzón de correo correspondiente. Las directivas de retención de Teams eliminarán estos mensajes del subproceso de Teams. Sin embargo, si el historial de conversaciones está activado para Skype empresarial online y desde el lado del cliente de Skype empresarial online, se guardan en un buzón de correo y los datos de la conversación no se controlan mediante una directiva de retención de Teams.

Las directivas de retención de Teams se basan en la fecha en que se crearon los mensajes de la conversación o el canal y que están retroactivas. En otras palabras, si crea una directiva de retención para eliminar los datos anteriores a 90 días, se eliminarán los datos de Team creados hace más de 90 días.

Es posible que una directiva de retención que se aplique a SharePoint Online o OneDrive para la empresa pueda eliminar un archivo al que se hace referencia en un chat de equipo o un mensaje de canal antes de que estos mensajes se eliminen. En este caso, el archivo seguirá apareciendo en el mensaje de Teams, pero cuando los usuarios hacen clic en el archivo, recibirán el error "no se encuentra el archivo". Esto también puede ocurrir en ausencia de una directiva, si alguien elimina manualmente un archivo de SharePoint Online o OneDrive para la empresa.

### <a name="considerations-and-limitations"></a>Consideraciones y limitaciones

Estas son algunas consideraciones y limitaciones que debe tener en cuenta al trabajar con directivas de retención de Teams:

- Teams necesita una directiva de retención que sea independiente de otras cargas de trabajo. En otras palabras, debe crear directivas de retención específicas para los chats de Teams y/o los mensajes de canal. Por esta razón, no puede incluir equipos en las directivas de retención de toda la organización.

- No se admiten mensajes de canal privado. En este momento, las directivas de retención para Teams solo se aplican a los mensajes de canal estándar.

- Teams no admite la configuración avanzada de retención, como la capacidad de aplicar una directiva a contenido que contiene palabras clave o información confidencial. Por el momento, las directivas de retención de Teams se aplican a todo el contenido de mensajes de chat y/o canales.

- Teams puede demorar hasta tres días en limpiar los mensajes caducados. Una directiva de retención de equipos eliminará los mensajes de chat y de canales cuando venza el período de retención. Sin embargo, puede demorar hasta tres días en limpiar estos mensajes y eliminarlos de forma permanente. Además, los mensajes de chats y canales se pueden buscar con herramientas de eDiscovery entre el momento en que vence el período de retención y cuando los mensajes se eliminan de forma permanente.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>Varias directivas de retención y los principios de la retención

Si configura varias directivas de retención de Teams con diversas duraciones, [rigen los principios de las directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) . A continuación se ofrece una descripción general de lo que tiene prioridad:

- Preservar siempre gana la eliminación
- El período de preservación más largo siempre gana
- La inclusión explícita prevalece sobre la inclusión implícita en términos de ubicaciones
- Gana el período de eliminación más corto

## <a name="when-to-use-retention-policies-for-teams"></a>Cuándo usar directivas de retención para equipos

En muchos casos, las organizaciones consideran que los datos de los chats privados son más responsabilidad de los mensajes de canal, que suelen ser más conversaciones relacionadas con el proyecto.

Puede configurar directivas de retención distintas para los chats privados (1:1 o 1: muchos chats) y mensajes de canal. También puede configurar directivas únicas que se apliquen a determinados usuarios o equipos de su organización. Para los chats de Teams, puede seleccionar a qué usuarios se aplica la Directiva. Para los mensajes de canal de Teams, puede seleccionar a qué equipos se aplica la Directiva.

Por ejemplo, para los mensajes de canal, puede aplicar una directiva de eliminación de un año a determinados equipos de su organización y aplicar una directiva de eliminación de tres años a todos los demás equipos.

## <a name="manage-retention-policies-for-teams"></a>Administrar directivas de retención para equipos

### <a name="using-the-security--compliance-center"></a>Usar el centro de cumplimiento de & de seguridad

#### <a name="create-a-retention-policy"></a>Crear una directiva de retención

Para crear una directiva de retención para los chats de Teams y los mensajes de canales, haga lo siguiente:

1. En el centro de navegación izquierdo del centro de cumplimiento de & de seguridad, vaya a**retención**de **gobierno** > de información.
2. Seleccione **crear**.
3. En la página **nombre de la Directiva** , escriba un nombre y una descripción para la Directiva y, a continuación, haga clic en **siguiente**.
4. En la página **configuración** , especifique si desea conservar los datos, eliminarlos, o ambos, el período de retención y, a continuación, haga clic en **siguiente**.
5. En la página **elegir ubicaciones** , siga este procedimiento y, a continuación, haga clic en **siguiente**:

    - Para aplicar la Directiva a los mensajes del canal, Active **los mensajes de canal de Teams**.  Si quiere aplicar la Directiva a determinados equipos de su organización, seleccione **elegir equipos**y, a continuación, seleccione los equipos que quiera.
    - Para aplicar la Directiva a los chats, active los **chats de Teams**. Si desea aplicar la Directiva a usuarios específicos de su organización, seleccione **elegir usuarios**y, a continuación, seleccione los usuarios que desee.
      > [!NOTE]
      > Al activar **los mensajes de canal de Teams o los** **chats de Teams**, todas las demás ubicaciones se desactivan automáticamente. Una directiva de retención de Teams solo puede incluir ubicaciones de Teams.

        ![Captura de pantalla de las opciones de mensajes de canal de Teams y chats de Teams en la página elegir ubicaciones](media/retention-policies-create.png)

      > [!IMPORTANT]
      > Los chats de equipos y los mensajes de canal no se ven afectados por las directivas de retención aplicadas a buzones de usuario o grupo en las ubicaciones de **correo electrónico de Exchange** o de **grupos de Office 365** . Aunque los chats de Teams y los mensajes de canal se almacenan en Exchange, solo se ven afectados por directivas de retención aplicadas a las ubicaciones de los equipos.

6. Revise la configuración y, cuando esté listo, seleccione **crear esta directiva**.

#### <a name="edit-a-retention-policy"></a>Editar una directiva de retención

Para editar una directiva de retención de Teams, haga lo siguiente:

1. En el centro de navegación izquierdo del centro de cumplimiento de & de seguridad, vaya a**retención**de **gobierno** > de información.
2. En la lista de directivas de retención, active la casilla situada junto a la Directiva de retención que desea editar.
3. Seleccione **Editar** junto a lo que desea editar, realice los cambios, haga clic en **Guardar**y, a continuación, haga clic en **cerrar**.

    ![Captura de pantalla de las opciones de mensajes de canal de Teams y chats de Teams en la página elegir ubicaciones](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>Eliminar una directiva de retención

Para eliminar una directiva de retención de Teams, haga lo siguiente:

1. En el centro de navegación izquierdo del centro de cumplimiento de & de seguridad, vaya a**retención**de **gobierno** > de información.
2. En la lista de directivas de retención, active la casilla situada junto a la Directiva de retención que desea eliminar.
3. Seleccione **eliminar Directiva**.

### <a name="using-powershell"></a>Usar PowerShell

Para crear y administrar directivas de retención de Teams mediante PowerShell, use los siguientes cmdlets.

|Políticas|Filete|
|---|---|
|[Nuevo: TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Nuevo: TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>Problemas conocidos

A continuación se muestran algunos problemas conocidos relacionados con las directivas de retención en Teams en los que se realiza el seguimiento e investigación.

- En **elegir equipos** en la fila ubicaciones de **los mensajes del canal de Teams** , es posible que vea Office 365 grupos que no son también equipos. Esto se corregirá en el futuro.

- En **elegir usuarios** en la fila ubicación de **chats de equipos** , es posible que vea invitados y usuarios que no sean buzones de correo. Las directivas de retención no se deben configurar para los invitados y estamos trabajando para eliminarlas de la lista.

- El Asistente de ciclo de vida de Exchange (ELC) se ejecuta diariamente, pero tiene un SLA de 7 días. Como resultado, es posible que, si tiene una directiva de retención de equipos para eliminar elementos anteriores a 60 días, estos elementos podrían persistir durante un máximo de 67 días. Esta no es una nueva situación: sigue el modelo de Exchange. Por supuesto, en la mayoría de los casos, no hay ningún retraso.

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
