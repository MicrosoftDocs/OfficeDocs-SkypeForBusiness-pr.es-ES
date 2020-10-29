---
title: Administrar sus dispositivos en Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Obtenga información sobre cómo administrar dispositivos usados con equipos de su organización.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40ddf36c27a8fbc3aadfddaddee886d1906bab82
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48793535"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Administrar sus dispositivos en Microsoft Teams

Puede administrar los dispositivos que se usan con Microsoft Teams en su organización desde el centro de administración de Microsoft Teams. Puede ver y administrar el inventario de dispositivos de su organización y realizar tareas como actualizar, reiniciar y supervisar los diagnósticos de los dispositivos. También puede crear y asignar perfiles de configuración a un dispositivo o a grupos de dispositivos.

Para administrar dispositivos, como cambiar la configuración de un dispositivo, reiniciar dispositivos, administrar actualizaciones o ver el estado de los dispositivos y periféricos, debe tener uno de los siguientes roles de administrador de Microsoft 365:

- Administrador global de Microsoft 365
- Administración de servicios de Teams
- Administrador de dispositivos de Teams

Para obtener más información sobre los roles de administrador de Teams, consulte [usar los roles de administrador de Teams para administrar equipos](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>¿Qué dispositivos puede administrar?

Puede administrar cualquier dispositivo que esté certificado e inscrito en Teams. Un dispositivo se inscribe automáticamente la primera vez que un usuario inicia sesión en Teams en el dispositivo. Para obtener una lista de los dispositivos certificados que se pueden administrar, consulte:

- [Salas de Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teléfonos de conferencia](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Teléfonos de escritorio](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams muestra](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Barras de colaboración](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Para administrar dispositivos, en el navegación izquierdo del [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com), vaya a **dispositivos** y, después, seleccione el tipo de dispositivo. Cada tipo de dispositivo tiene su propia sección respectiva, que le permite administrarlos por separado.

## <a name="manage-teams-rooms-devices"></a>Administrar dispositivos de salas de equipos

Puede usar el centro de administración de Teams para ver y administrar de forma remota los dispositivos de las salas de sus equipos en toda la organización. El centro de administración de Teams facilita la consulta, de un vistazo, de qué dispositivos son correctos y cuáles necesitan atención y le permite centrarse en dispositivos específicos para ver información detallada sobre el estado del dispositivo, la calidad de las llamadas, la calidad de las llamadas y los periféricos. 

Estas son algunas de las cosas que puede hacer para administrar los dispositivos de las salas de equipos. Los dispositivos de salas de equipos pueden encontrarse en el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com) en **dispositivos**  >  **salas de equipos** .

Para obtener detalles sobre cómo administrar los dispositivos de salas de equipos, consulte [administrar salas de Microsoft Teams](../rooms/rooms-manage.md).

| Para hacer esto... | Haga lo siguiente|
|---------------|--------|
| Cambiar la configuración en uno o más dispositivos | Seleccione uno o más dispositivos > **Editar configuración** . Si selecciona varios dispositivos, los valores que cambie reemplazarán los valores de todos los dispositivos seleccionados. |
| Reiniciar dispositivos | Seleccione uno o más dispositivos > **reiniciar** . Cuando reinicia un dispositivo, puede elegir si desea reiniciar el dispositivo inmediatamente o seleccionar **Schedule restart** para que reinicie el dispositivo en una fecha y hora específicas. La fecha y la hora que seleccione son locales para el dispositivo que se va a reiniciar.|
| Ver actividad de reunión | Seleccione un nombre de dispositivo para abrir detalles del dispositivo > **actividad** . Al abrir la pestaña **actividad** , puede ver todas las reuniones en las que ha participado el dispositivo. Esta vista de resumen muestra la hora de inicio de la reunión, el número de participantes, su duración y la calidad general de las llamadas.|
| Ver detalles de la reunión |  Seleccione un nombre de dispositivo para abrir detalles del dispositivo > **actividad** > Seleccione una reunión. Al abrir los detalles de una reunión, puede ver a todos los participantes de la reunión, cuánto tiempo se encontraban en la llamada, los tipos de sesión de Teams y la calidad de las llamadas individuales. Si desea ver información técnica sobre la llamada de un participante, seleccione la hora de inicio de la llamada del participante.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Administrar teléfonos, barras de colaboración y equipos 

En el centro de administración de Teams, puede ver y administrar teléfonos, barras de colaboración y equipos que se han inscrito en Teams en su organización. La información que verás para cada dispositivo incluye el nombre del dispositivo, el fabricante, el modelo, el usuario, el estado, la acción, la última vista y el historial. Puede personalizar la vista para que muestre la información que se adapte a sus necesidades.

Los teléfonos, las barras de colaboración y las pantallas de Teams se inscribión automáticamente en Microsoft Intune si se ha suscrito a él. Una vez que se ha inscrito un dispositivo, se confirma el cumplimiento del dispositivo y se aplican las directivas de acceso condicional al dispositivo.

A continuación se muestran algunos ejemplos de cómo puede administrar teléfonos, barras de colaboración y equipos en la organización.  

|Para hacer esto...  |Haga lo siguiente |
|---------|---------|
| Cambiar la información del dispositivo               | Seleccione un dispositivo > **Editar** . Puede editar detalles como el nombre del dispositivo, la etiqueta de activos y agregar notas.     |
| Administrar actualizaciones de software                 | Seleccione un dispositivo > **Actualizar** . Puede ver la lista de actualizaciones de software y firmware disponibles para el dispositivo y elegir las actualizaciones que desea instalar. Para obtener más información sobre cómo actualizar dispositivos, consulte [actualizar dispositivos de forma remota](remote-update.md)   |
| Mostrar la actualización de equipos a equipos                | En la página **teléfonos IP** , seleccione uno o más teléfonos de teams > **Actualizar** . Esta opción solo está disponible para los teléfonos que son compatibles con la actualización a teams. Para obtener más información, vea [Actualizar teléfonos a equipos de](upgrade-phones-to-displays.md)Teams.   |
| Asignar o cambiar directivas de configuración | Seleccione uno o más dispositivos > **asignar configuración** .                                                                                                                                                                                                                   |
| Agregar o quitar etiquetas de dispositivo               | Seleccione uno o más dispositivos > **administrar etiquetas** . Para obtener más información sobre las etiquetas de dispositivo, vea [administrar etiquetas de dispositivo de Teams](manage-device-tags.md).                                                                                                      |
| Reiniciar dispositivos                         | Seleccione uno o más dispositivos > **reiniciar** .                                                                                                                                                                                                                                |
| Filtrar dispositivos con etiquetas de dispositivo        | Seleccione el icono de filtro, seleccione el campo de **etiqueta** , especifique una etiqueta de dispositivo para filtrar y seleccione **aplicar** . Para obtener más información sobre el filtrado de dispositivos con etiquetas de dispositivo, vea [usar filtros para devolver dispositivos con una etiqueta específica](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag).|
| Ver el historial del dispositivo                     | Seleccione un dispositivo > **historial** . Puede ver el historial de actualizaciones del dispositivo.                                                                                                                                                                                |
| Ver diagnósticos                        | Seleccione un dispositivo > **diagnósticos** .                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Usar perfiles de configuración en Teams

Use perfiles de configuración para administrar la configuración y las características de los teléfonos y las barras de colaboración de su organización. Puede crear o cargar perfiles de configuración para incluir opciones y características que desee habilitar o deshabilitar y, después, asignar un perfil a un dispositivo o a grupos de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Crear un perfil de configuración

1. En el navegación de la izquierda, vaya a perfiles de configuración de **dispositivos**  >  **Configuration profiles** .
2. Haga clic en **Agregar** .
3. Escriba un nombre para el perfil y, si lo desea, agregue una descripción.
4. Especifique la configuración que desee para el perfil y, a continuación, haga clic en **Guardar** .

#### <a name="assign-a-configuration-profile"></a>Asignar un perfil de configuración

1. En el navegación de la izquierda, vaya a perfiles de configuración de **dispositivos**  >  **Configuration profiles** .
2. Seleccione el **Perfil de configuración** que desea asignar y, a continuación, haga clic en **asignar al dispositivo** .  
3. En el panel **asignar dispositivos a un perfil de configuración** , busque y seleccione los dispositivos que desea asignar.
4. Haga clic en **Guardar** .

