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
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 576c22d95dbbbb16105eb8e365c717ba7140cfb8
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65767246"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams: administrar los dispositivos 

Puede administrar los dispositivos que se usan con Microsoft Teams en su organización desde el centro de administración de Microsoft Teams. Puedes ver y administrar el inventario de dispositivos de tu organización y realizar tareas como actualizar, reiniciar y supervisar los diagnósticos de dispositivos. También puede crear y asignar perfiles de configuración a un dispositivo o grupos de dispositivos.

Para administrar dispositivos, como cambiar la configuración del dispositivo, reiniciar dispositivos, administrar actualizaciones o ver el estado de los dispositivos y periféricos, debes tener asignado uno de los siguientes roles de administrador Microsoft 365:

- Microsoft 365 administrador global
- Teams administrador del servicio
- Teams administrador de dispositivos

Para obtener más información sobre los roles de administrador en Teams, vea [Usar roles de administrador Teams para administrar Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>¿Qué dispositivos puedes administrar?

Puede administrar cualquier dispositivo certificado para Teams e inscrito. Un dispositivo se inscribe automáticamente la primera vez que un usuario inicia sesión en Teams en el dispositivo. Para obtener una lista de los dispositivos certificados que se pueden administrar, consulte:

- [Salas de Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teléfonos de conferencia](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Teléfonos de escritorio](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams pantallas](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [paneles Teams](teams-panels.md)

Para administrar dispositivos, en el panel de navegación izquierdo del [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com), ve a **Teams Dispositivos** y, a continuación, selecciona el tipo de dispositivo. Cada tipo de dispositivo tiene su propia sección correspondiente, que te permite administrarlos por separado.

## <a name="manage-teams-rooms-on-windows-devices"></a>Administrar Salas de Teams en dispositivos Windows

Puede usar el centro de administración de Teams para ver y administrar de forma remota su Salas de Teams en Windows dispositivos de su organización. El centro de administración de Teams facilita ver, de un vistazo, qué dispositivos están en buen estado y cuáles necesitan atención, y le permite centrarse en dispositivos específicos para ver información detallada sobre el estado del dispositivo, el rendimiento de las reuniones, la calidad de las llamadas y los periféricos. 

Estas son algunas de las cosas que puedes hacer para administrar los dispositivos Salas de Teams. Salas de Teams dispositivos se pueden encontrar en el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com), en **Dispositivos** >  Teams **Salas de Teams en Windows**.

Para obtener más información sobre cómo administrar los dispositivos Salas de Teams, consulta [Administrar Salas de Microsoft Teams](../rooms/rooms-manage.md).

| Para ello...                          | Haz esto                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cambiar la configuración en uno o más dispositivos | Selecciona uno o más dispositivos > **Editar configuración**. Si selecciona varios dispositivos, los valores que cambie reemplazarán los valores de todos los dispositivos seleccionados.                                                                                                                                                                                                                       |
| Reiniciar dispositivos                        | Selecciona uno o más dispositivos > **Reiniciar**. Al reiniciar un dispositivo, puedes elegir si quieres reiniciar el dispositivo inmediatamente o seleccionar **Programar reinicio** para reiniciar el dispositivo en una fecha y hora específicas. La fecha y hora que selecciones son locales en el dispositivo que se reiniciará.                                                                                            |
| Ver la actividad de la reunión                  | Selecciona un nombre de dispositivo para abrir los detalles del dispositivo > **Actividad**. Al abrir la pestaña **Actividad** , puede ver todas las reuniones en las que ha participado el dispositivo. Esta vista de resumen muestra la hora de inicio de la reunión, el número de participantes, su duración y la calidad general de la llamada.                                                                                        |
| Ver detalles de la reunión                   | Seleccione un nombre de dispositivo para abrir los detalles del dispositivo > **Actividad** > seleccione una reunión. Al abrir los detalles de una reunión, puede ver todos los participantes de la reunión, cuánto tiempo estuvieron en la llamada, los tipos de sesión Teams y su calidad de llamada individual. Si desea ver información técnica sobre la llamada de un participante, seleccione la hora de inicio de la llamada del participante. |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>Administrar teléfonos, Salas de Teams en Android, pantallas Teams y paneles Teams 

En el centro de administración de Teams, puede ver y administrar teléfonos, Salas de Teams en Android, pantallas Teams y paneles de Teams inscritos en Teams de su organización. La información que verás para cada dispositivo incluye el nombre del dispositivo, el fabricante, el modelo, el usuario, el estado, la acción, la última vista y el historial. Puede personalizar la vista para mostrar la información que se ajuste a sus necesidades.

Los teléfonos, Salas de Teams en Android, pantallas de Teams y paneles de Teams se inscriben automáticamente en Microsoft Intune si se ha suscrito a él. Después de inscribir un dispositivo, se confirma el cumplimiento del dispositivo y se aplican directivas de acceso condicional al dispositivo.

Estos son algunos ejemplos de cómo puede administrar teléfonos, Salas de Teams en Android, pantallas Teams y paneles de Teams de su organización.  

| Para ello...                           | Haz esto                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cambiar la información del dispositivo               | Seleccione un dispositivo > **Editar**. Puede editar detalles como el nombre del dispositivo, la etiqueta de activo y agregar notas.                                                                                                                                                                                                              |
| Administrar actualizaciones de software                 | Selecciona un dispositivo > **Actualizar**. Puedes ver la lista de actualizaciones de software y firmware disponibles para el dispositivo y elegir las actualizaciones que se instalarán. Para obtener más información sobre la actualización de dispositivos, consulta [Actualizar Teams dispositivos de forma remota](remote-update.md).                                                          |
| Actualizar los teléfonos Teams a pantallas Teams  | En la página **Teléfonos IP**, selecciona uno o varios teléfonos Teams > **Actualizar**. Esta opción solo está disponible para los teléfonos que admiten la actualización a pantallas de Teams. Para obtener más información, consulta [Actualizar los teléfonos Teams a pantallas de Teams](upgrade-phones-to-displays.md).                                                      |
| Asignar o cambiar directivas de configuración | Selecciona uno o más dispositivos > **Asignar configuración**.                                                                                                                                                                                                                                                       |
| Agregar o quitar etiquetas de dispositivo               | Selecciona uno o más dispositivos > **Administrar etiquetas**. Para obtener más información sobre las etiquetas de dispositivo, consulta [Administrar Teams etiquetas de dispositivo](manage-device-tags.md).                                                                                                                                                                 |
| Reiniciar dispositivos                         | Selecciona uno o más dispositivos > **Reiniciar**.                                                                                                                                                                                                                                                                    |
| Filtrar dispositivos con etiquetas de dispositivo        | Selecciona el icono de filtro, selecciona el campo **Etiqueta** , especifica una etiqueta de dispositivo por la que filtrar y selecciona **Aplicar**. Para obtener más información sobre cómo filtrar dispositivos con etiquetas de dispositivo, consulta [Usar filtros para devolver dispositivos con una etiqueta específica](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Ver el historial y los diagnósticos del dispositivo     | En la columna **Historial** , haz clic en el vínculo **Ver** de un dispositivo para ver su historial de actualizaciones y los detalles de diagnóstico.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Usar perfiles de configuración en Teams

Use perfiles de configuración para administrar la configuración y las características de los distintos dispositivos Teams de su organización, incluidos los Salas de Teams en Android, pantallas Teams, teléfonos Teams y paneles de Teams. Puede crear o cargar perfiles de configuración para incluir las opciones y características que desea habilitar o deshabilitar y, a continuación, asignar un perfil a un dispositivo o conjunto de dispositivos. 

#### <a name="create-a-configuration-profile"></a>Crear un perfil de configuración

Para crear un perfil de configuración para un tipo de dispositivo Teams:

1. En el panel de navegación izquierdo, ve a **Teams Dispositivos** > selecciona el tipo de dispositivo Teams > **Perfiles de configuración**. Por ejemplo, seleccione **Dispositivos** >  Teams **Teams paneles** > **Perfiles de configuración** para crear un nuevo perfil de configuración para Teams paneles.
2. Haga clic en **Agregar**.
3. Escriba un nombre para el perfil y, opcionalmente, agregue una descripción sencilla.
4. Especifique la configuración que desee para el perfil y, a continuación, haga clic en **Guardar**.
   El perfil de configuración recién creado aparece en la lista de perfiles.

#### <a name="assign-a-configuration-profile"></a>Asignar un perfil de configuración
Después de crear un perfil de configuración para un tipo de dispositivo Teams, asígnelo a uno o más dispositivos.

1. En el panel de navegación izquierdo, ve a **Teams Dispositivos** > selecciona el tipo de dispositivo Teams. Por ejemplo, para asignar un perfil de configuración a un dispositivo de paneles Teams, seleccione **Dispositivos** >  Teams **Teams paneles**.
2. Seleccione uno o más dispositivos y, a continuación, haga clic en **Asignar configuración**.  
3. En el panel **Asignar una configuración** , busque el perfil de configuración para asignarlo a los dispositivos seleccionados.
4. Haga clic en **Aplicar**.
   Para los dispositivos a los que aplicó la directiva de configuración, la columna **Acción** muestra **Actualización de** configuración y la columna **Perfil** de configuración muestra el nombre del perfil de configuración.
