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
description: Obtenga información sobre cómo administrar dispositivos usados con Teams en su organización.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41213955c9e57829208ce0ec98448195dc266044
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2021
ms.locfileid: "50350606"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Administrar sus dispositivos en Microsoft Teams

Puede administrar dispositivos usados con Microsoft Teams en su organización desde el Centro de administración de Microsoft Teams. Puede ver y administrar el inventario de dispositivos de su organización y realizar tareas como actualizar, reiniciar y supervisar diagnósticos para dispositivos. También puede crear y asignar perfiles de configuración a un dispositivo o grupos de dispositivos.

Para administrar dispositivos, como cambiar la configuración del dispositivo, reiniciar dispositivos, administrar actualizaciones o ver el estado de los dispositivos y periféricos, debe tener asignado uno de los siguientes roles de administrador de Microsoft 365:

- Administrador global de Microsoft 365
- Administrador del servicio de Teams
- Administrador de dispositivos de Teams

Para obtener más información sobre los roles de administrador en Teams, vea [Usar roles de administrador de Teams para administrar Teams.](../using-admin-roles.md)

## <a name="what-devices-can-you-manage"></a>¿Qué dispositivos puede administrar?

Puede administrar cualquier dispositivo certificado para Teams y inscrito en él. Un dispositivo se inscribe automáticamente la primera vez que un usuario inicia sesión en Teams en el dispositivo. Para obtener una lista de dispositivos certificados que se pueden administrar, vea:

- [Barras de colaboración](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Teléfonos de conferencia](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Teléfonos de escritorio](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Salas de Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Se muestra Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Paneles de Teams](teams-panels.md)

Para administrar dispositivos, en la navegación izquierda del Centro de administración de [Microsoft Teams,](https://admin.teams.microsoft.com)vaya a **Dispositivos** y, a continuación, seleccione el tipo de dispositivo. Cada tipo de dispositivo tiene su propia sección respectiva, que le permite administrarlos por separado.

## <a name="manage-teams-rooms-devices"></a>Administrar dispositivos de Salas de Teams

Puede usar el Centro de administración de Teams para ver y administrar de forma remota los dispositivos de salas de Teams en toda la organización. El Centro de administración de Teams permite ver fácilmente, de un vistazo, qué dispositivos están en buen estado y que necesitan atención, y le permite centrarse en dispositivos específicos para ver información detallada sobre el estado del dispositivo, el rendimiento de las reuniones, la calidad de las llamadas y los periféricos. 

Estas son algunas de las cosas que puede hacer para administrar los dispositivos de Salas de Teams. Los dispositivos salas de Teams se pueden encontrar en el Centro de administración de [Microsoft Teams](https://admin.teams.microsoft.com) en **Salas** de Teams  >  **de dispositivos.**

Para obtener más información sobre cómo administrar los dispositivos de Salas de Teams, vea [Administrar salas de Microsoft Teams.](../rooms/rooms-manage.md)

| Para ello...                          | Haga lo siguiente                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cambiar la configuración en uno o varios dispositivos | Seleccione uno o varios dispositivos > **configuración de edición.** Si selecciona varios dispositivos, los valores que cambie reemplazarán los valores de todos los dispositivos seleccionados.                                                                                                                                                                                                                       |
| Reiniciar dispositivos                        | Seleccione uno o varios dispositivos > **Reiniciar**. Al reiniciar un dispositivo, puede elegir si desea  reiniciar el dispositivo inmediatamente o seleccionar Programar reinicio para reiniciar el dispositivo en una fecha y hora específicas. La fecha y hora que seleccione es local para el dispositivo que se está reiniciando.                                                                                            |
| Ver la actividad de la reunión                  | Seleccione un nombre de dispositivo para abrir los detalles del > **actividad**. Al abrir la **pestaña Actividad,** puede ver todas las reuniones en las que ha participado el dispositivo. Esta vista de resumen muestra la hora de inicio de la reunión, el número de participantes, su duración y la calidad global de la llamada.                                                                                        |
| Ver detalles de la reunión                   | Seleccione un nombre de dispositivo para abrir los detalles del > **actividad >** una reunión. Al abrir los detalles de una reunión, puede ver todos los participantes de la reunión, cuánto tiempo estuvieron en la llamada, los tipos de sesión de Teams y su calidad de llamada individual. Si desea ver información técnica sobre la llamada de un participante, seleccione la hora de inicio de la llamada del participante. |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>Administrar teléfonos, barras de colaboración, pantallas de Teams y paneles de Teams 

En el Centro de administración de Teams, puede ver y administrar teléfonos, barras de colaboración, pantallas de Teams y paneles de Teams inscritos en Teams en su organización. La información que verá para cada dispositivo incluye el nombre del dispositivo, el fabricante, el modelo, el usuario, el estado, la acción, la última vista y el historial. Puede personalizar la vista para mostrar la información que se adapte a sus necesidades.

Los teléfonos, las barras de colaboración, las pantallas de Teams y los paneles de Teams se inscriben automáticamente en Microsoft Intune si se ha registrado para ello. Después de inscribir un dispositivo, se confirma el cumplimiento del dispositivo y se aplican directivas de acceso condicional al dispositivo.

Estos son algunos ejemplos de cómo puede administrar teléfonos, barras de colaboración, pantallas de Teams y paneles de Teams en su organización.  

| Para ello...                           | Haga lo siguiente                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cambiar la información del dispositivo               | Seleccione un dispositivo > **Editar**. Puede editar detalles como el nombre del dispositivo, la etiqueta de activo y agregar notas.                                                                                                                                                                                                              |
| Administrar actualizaciones de software                 | Seleccione un dispositivo > **Actualizar**. Puede ver la lista de actualizaciones de software y firmware disponibles para el dispositivo y elegir las actualizaciones que desea instalar. Para obtener más información sobre cómo actualizar dispositivos, vea [Actualizar dispositivos de Teams de forma remota](remote-update.md)                                                          |
| Actualizar los teléfonos de Teams a las pantallas de Teams  | En la **página Teléfonos IP,** seleccione uno o varios teléfonos de Teams > **actualizar.** Esta opción solo está disponible para los teléfonos que admiten la actualización a las pantallas de Teams. Para obtener más información, vea [Actualizar los teléfonos de Teams a las pantallas de Teams.](upgrade-phones-to-displays.md)                                                      |
| Asignar o cambiar directivas de configuración | Seleccione uno o varios dispositivos > **Asignar configuración.**                                                                                                                                                                                                                                                       |
| Agregar o quitar etiquetas de dispositivo               | Seleccione uno o varios dispositivos > **Administrar etiquetas.** Para obtener más información sobre las etiquetas de dispositivo, vea [Administrar etiquetas de dispositivo de Teams.](manage-device-tags.md)                                                                                                                                                                 |
| Reiniciar dispositivos                         | Seleccione uno o varios dispositivos > **Reiniciar**.                                                                                                                                                                                                                                                                    |
| Filtrar dispositivos con etiquetas de dispositivo        | Seleccione el icono de filtro, seleccione el **campo Etiqueta,** especifique una etiqueta de dispositivo en la que filtrar y seleccione **Aplicar.** Para obtener más información sobre cómo filtrar dispositivos con etiquetas de dispositivo, vea [Usar filtros para devolver dispositivos con una etiqueta específica.](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag) |
| Ver el historial de dispositivos y diagnósticos     | En la **columna** Historial, haga clic **en** el vínculo Ver de un dispositivo para ver su historial de actualizaciones y detalles diagosticos.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Usar perfiles de configuración en Teams

Use perfiles de configuración para administrar la configuración y las características de diferentes dispositivos de Teams de su organización, incluidas las barras de colaboración, las pantallas de Teams, el teléfono de Teams y los paneles de Teams. Puede crear o cargar perfiles de configuración para incluir la configuración y las características que desea habilitar o deshabilitar y, a continuación, asignar un perfil a un dispositivo o conjunto de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Crear un perfil de configuración

Para crear un perfil de configuración para un tipo de dispositivo de Teams:

1. En el panel de navegación izquierdo, vaya a **Dispositivos** > seleccione el tipo de dispositivo de Teams > **perfiles de configuración.** Por ejemplo, seleccione **Paneles de**  >  **Dispositivos Teams**  >  **Perfiles de configuración** para crear un nuevo perfil de configuración para paneles de Teams.
2. Haga clic en **Agregar**.
3. Escriba un nombre para el perfil y, opcionalmente, agregue una descripción descriptivo.
4. Especifique la configuración que desea para el perfil y, a continuación, haga clic en **Guardar.**
   El perfil de configuración recién creado se muestra en la lista de perfiles.

#### <a name="assign-a-configuration-profile"></a>Asignar un perfil de configuración
Después de crear un perfil de configuración para un tipo de dispositivo de Teams, asígnelo a uno o varios dispositivos.

1. En el panel de navegación izquierdo, vaya **a Dispositivos** > seleccione el tipo de dispositivo de Teams. Por ejemplo, para asignar un perfil de configuración a un dispositivo de paneles de Teams, seleccione **Paneles de Devices**  >  **Teams.**
2. Seleccione uno o varios dispositivos y, a continuación, haga clic **en Asignar configuración.**  
3. En el **panel Asignar una configuración,** busque el perfil de configuración que desea asignar a los dispositivos seleccionados.
4. Haga clic en **Aplicar**.
   Para los dispositivos a los que aplicó  la directiva  de configuración, la columna Acción muestra Actualización de configuración y la columna Perfil de configuración muestra el nombre del perfil de configuración. 
