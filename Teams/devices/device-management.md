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
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Obtenga información sobre cómo administrar los dispositivos que se usan con Teams en su organización.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6996b0980ae7305a7517a71645ba823a588e2f8
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033019"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Administrar sus dispositivos en Microsoft Teams

Puede administrar los dispositivos que se usan con Microsoft Teams en su organización desde el Centro de administración de Microsoft Teams. Puede ver y administrar el inventario de dispositivos de su organización y realizar tareas como actualizar, reiniciar y supervisar el diagnóstico de los dispositivos. También puede crear y asignar perfiles de configuración a un dispositivo o grupos de dispositivos.

Para administrar dispositivos, como cambiar la configuración del dispositivo, reiniciar dispositivos, administrar actualizaciones o ver el dispositivo y el estado de los periféricos, debe tener asignado uno de los siguientes roles de administrador de Microsoft 365:

- Administrador global de Microsoft 365
- Administrador del servicio de Teams
- Administrador de dispositivos de Teams

Para obtener más información sobre los roles de administrador en Teams, [consulte Usar roles de administrador de Teams para administrar Teams.](../using-admin-roles.md)

## <a name="what-devices-can-you-manage"></a>¿Qué dispositivos puede administrar?

Puede administrar cualquier dispositivo que se haya certificado para Teams e inscrito en él. La primera vez que un usuario inicia sesión en Teams en el dispositivo, se inscribe automáticamente un dispositivo. Para obtener una lista de los dispositivos certificados que se pueden administrar, vea:

- [Salas de Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teléfonos de conferencia](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Teléfonos de escritorio](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams muestra](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Barras de colaboración](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Para administrar dispositivos, en el panel de navegación izquierdo del Centro de administración de [Microsoft Teams,](https://admin.teams.microsoft.com)vaya a Dispositivos **y,** a continuación, seleccione el tipo de dispositivo. Cada tipo de dispositivo tiene su propia sección correspondiente, que te permite administrarlos por separado.

## <a name="manage-teams-rooms-devices"></a>Administrar dispositivos de Salas de Teams

Puede usar el Centro de administración de Teams para ver y administrar de forma remota los dispositivos de Salas de Teams en toda su organización. El Centro de administración de Teams le permite ver fácilmente, de un vistazo, qué dispositivos están en buen estado y que necesitan atención, y le permite centrarse en dispositivos específicos para ver información detallada sobre el estado del dispositivo, el rendimiento de las reuniones, la calidad de la llamada y los periféricos. 

Estas son algunas de las cosas que puede hacer para administrar sus dispositivos de Salas de Teams. Los dispositivos de salas de Teams se pueden encontrar en el centro de administración de [Microsoft Teams,](https://admin.teams.microsoft.com) **en** Salas de equipos de  >  **dispositivos.**

Para obtener más información sobre cómo administrar sus dispositivos de salas de Teams, consulte [Administrar salas de Microsoft Teams.](../rooms/rooms-manage.md)

| Para hacer esto... | Haga lo siguiente|
|---------------|--------|
| Cambiar la configuración en uno o más dispositivos | Seleccione uno o más dispositivos > **Editar configuración.** Si selecciona varios dispositivos, los valores que cambie reemplazarán los valores de todos los dispositivos seleccionados. |
| Reiniciar dispositivos | Seleccione uno o más dispositivos > **Reiniciar.** Al reiniciar un dispositivo, puede elegir si desea  reiniciar el dispositivo inmediatamente o seleccionar Programar reinicio para reiniciar el dispositivo en una fecha y hora específicas. La fecha y hora que selecciones son locales en el dispositivo que se reiniciará.|
| Ver la actividad de la reunión | Selecciona el nombre de un dispositivo para abrir los detalles del > **actividad.** Al abrir la **pestaña Actividad,** puede ver todas las reuniones en las que ha participado el dispositivo. Esta vista de resumen muestra la hora de inicio de la reunión, el número de participantes, su duración y la calidad general de la llamada.|
| Ver detalles de la reunión |  Seleccione el nombre del dispositivo para abrir los detalles del > **actividad >** seleccione una reunión. Al abrir los detalles de una reunión, puede ver todos los participantes de la reunión, cuánto tiempo han estado en la llamada, los tipos de sesión de Teams y su calidad de llamada individual. Si desea ver información técnica sobre la llamada de un participante, seleccione la hora de inicio de la llamada del participante.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Administrar teléfonos, barras de colaboración y pantallas de Teams 

En el Centro de administración de Teams, puede ver y administrar teléfonos, barras de colaboración y pantallas de Teams inscritos en Teams en su organización. La información que verás para cada dispositivo incluye el nombre del dispositivo, fabricante, modelo, usuario, estado, acción, última vista e historial. Puede personalizar la vista para mostrar la información que se ajuste a sus necesidades.

Los teléfonos, las barras de colaboración y las pantallas de Teams se inscriben automáticamente en Microsoft Intune si se ha registrado para ello. Una vez inscrito un dispositivo, se confirma el cumplimiento del dispositivo y se aplican directivas de acceso condicional al dispositivo.

Estos son algunos ejemplos de cómo administrar teléfonos, barras de colaboración y pantallas de Teams en su organización.  

|Para hacer esto...  |Haga lo siguiente |
|---------|---------|
| Cambiar la información del dispositivo               | Seleccione un dispositivo > **Editar.** Puede editar detalles como el nombre del dispositivo, la etiqueta de activos y agregar notas.     |
| Administrar actualizaciones de software                 | Seleccione un dispositivo > **Actualizar.** Puede ver la lista de actualizaciones de firmware y software disponibles para el dispositivo y elegir las actualizaciones que desea instalar. Para obtener más información sobre cómo actualizar dispositivos, consulte [Actualizar dispositivos de Teams de forma remota](remote-update.md)   |
| Actualizar los teléfonos de Teams a las pantallas de Teams                | En la **página teléfonos IP,** seleccione uno o varios teléfonos de Teams > **actualizar.** Esta opción solo está disponible en teléfonos que admiten la actualización a Teams. Para obtener más información, consulte [Actualizar los teléfonos de Teams a las pantallas de Teams.](upgrade-phones-to-displays.md)   |
| Asignar o cambiar directivas de configuración | Seleccione uno o más dispositivos > **Asignar configuración.**                                                                                                                                                                                                                   |
| Agregar o quitar etiquetas de dispositivo               | Seleccione uno o más dispositivos > **Administrar etiquetas.** Para obtener más información sobre las etiquetas de dispositivo, vea [Administrar etiquetas de dispositivo de Teams.](manage-device-tags.md)                                                                                                      |
| Reiniciar dispositivos                         | Seleccione uno o más dispositivos > **Reiniciar.**                                                                                                                                                                                                                                |
| Filtrar dispositivos con etiquetas de dispositivo        | Seleccione el icono de filtro, seleccione el **campo Etiqueta,** especifique una etiqueta de dispositivo por la que filtrar y seleccione **Aplicar.** Para obtener más información sobre cómo filtrar dispositivos con etiquetas de dispositivo, vea [Usar filtros para devolver dispositivos con una etiqueta específica.](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)|
| Ver el historial de dispositivos                     | Seleccione un dispositivo > **Historial.** Puede ver el historial de actualizaciones del dispositivo.                                                                                                                                                                                |
| Ver diagnósticos                        | Seleccione un dispositivo > **diagnóstico.**                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Usar perfiles de configuración en Teams

Use perfiles de configuración para administrar la configuración y las características de los teléfonos de Teams y las barras de colaboración de su organización. Puede crear o cargar perfiles de configuración para incluir las opciones y características que desea habilitar o deshabilitar y, a continuación, asignar un perfil a un dispositivo o grupos de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Crear un perfil de configuración

1. En el panel de navegación izquierdo, vaya a  >  **Perfiles de configuración de dispositivos.**
2. Haga clic en **Agregar**.
3. Escriba un nombre para el perfil y, si lo desea, agregue una descripción fácil de usar.
4. Especifique la configuración que desea para el perfil y, a continuación, haga clic en **Guardar.**

#### <a name="assign-a-configuration-profile"></a>Asignar un perfil de configuración

1. En el panel de navegación izquierdo, vaya a  >  **Perfiles de configuración de dispositivos.**
2. Seleccione el **perfil de configuración** que desea asignar y, a continuación, haga clic en Asignar al **dispositivo.**  
3. En el **panel Asignar dispositivos a un perfil de** configuración, busque y seleccione los dispositivos que desea asignar.
4. Haga clic en **Guardar**.

