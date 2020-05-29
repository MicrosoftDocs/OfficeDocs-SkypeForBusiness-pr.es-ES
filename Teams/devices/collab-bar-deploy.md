---
title: Implementar barras de colaboración para Microsoft Teams
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este artículo para obtener información sobre la implementación de barras de colaboración para Microsoft Teams.
ms.openlocfilehash: 71f9482dd5f42ddeb56b32c1a92db033d1f179f7
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410455"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Implementar barras de colaboración para Microsoft Teams

La implementación de las barras de colaboración de Microsoft Teams se puede dividir en las siguientes fases:

- **Disponibilidad del sitio** Confirme que las ubicaciones de la implementación (salas) cumplan con los requisitos de implementación.
- **Preparación del servicio** Crear cuentas de recursos y asignarlas a los dispositivos ([consulte crear una cuenta de recursos mediante el centro de administración de Microsoft 365](resource-account-ui.md)). Aunque se recomienda usar una licencia de sala dedicada, una cuenta de usuario final con licencia adecuada también puede iniciar sesión en las barras de colaboración.
- **Configuración e implementación** Configure las barras de colaboración en salas y conecte los dispositivos periféricos que necesite (consulte la documentación del fabricante para sus barras de colaboración).

## <a name="site-readiness"></a>Disponibilidad del sitio

Mientras los dispositivos pedidos están siendo enviados a su organización, trabaje con las redes, los servicios y los equipos de audio y vídeo para asegurarse de que se cumplan los requisitos de implementación y de que todos los sitios y salas estén listos en términos de energía, redes y pantalla.

Nuestras recomendaciones para los sitios de la barra de colaboración son:

- Salas de hasta 4 personas de tamaño
- Cuentas de recursos dedicadas
- Pantallas táctiles
- Cableado Ethernet
- Calidad de servicio (QoS) habilitada en la red para los medios de Microsoft Teams

Para obtener información sobre la instalación física, consulte la documentación del fabricante y, si tiene una, aproveche la experiencia de su equipo audiovisual antes de instalar y montar pantallas, y de los cables.

> [!TIP]
> Asegúrese de estar preparado para [preparar su red para los equipos](../prepare-network.md) para planear el ancho de banda y evaluar la idoneidad de su red para el tráfico en tiempo real.
>
> No se recomienda ubicar servidores proxy entre dispositivos de equipos e Internet. Para obtener más información sobre los equipos y servidores proxy, consulte [servidores proxy para Teams](../proxy-servers-for-skype-for-business-online.md).

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que sus sitios cumplen con los requisitos de disponibilidad de sitio para las barras de colaboración de Microsoft Teams.</li><li>Confirme que ha proporcionado suficiente ancho de banda para cada sitio.</li></ul>|
| ![Un icono que muestra los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comience a planificar la implementación y la configuración de la barra de colaboración.</li></ul>|

## <a name="service-readiness"></a>Preparación del servicio

Antes de implementar las barras de colaboración, debe decidir si usarán cuentas de recursos de Microsoft 365, cuentas de usuario final o una combinación de ambas. Las cuentas de recursos de Microsoft 365 son cuentas de buzón y de equipo dedicadas a recursos específicos, como una sala, un proyector, etc. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones con reglas que usted define al crearlas. A menos que una barra de colaboración esté dedicada a una persona específica para su uso privado, le recomendamos que configure una cuenta de recursos de Microsoft 365 para él.

### <a name="using-a-resource-account"></a>Uso de una cuenta de recursos

Si decide configurar una cuenta de recursos de Microsoft 365, tendrá que comprar una licencia de sala de reuniones para él. La licencia de la sala de reuniones incluye un buzón de recursos que permite a las personas de su organización reservar la sala de reuniones a través de Outlook o Teams. La licencia también habilita las conferencias de audio y vídeo y la pantalla compartida entre los participantes de la reunión.

Si necesita recibir o llamar a o desde un número de teléfono externo, es posible que necesite un plan de llamadas o una [licencia de complemento de](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)voz de Microsoft 365 empresa. Si tiene habilitado el enrutamiento directo en su organización, solo necesitará la SKU de la sala de reuniones.

Al crear una cuenta de recursos, puede elegir si desea permitir que la cuenta acepte o rechace automáticamente las convocatorias de reunión, que permita reuniones periódicas, especifique la antelación con la que los usuarios pueden reservar el recurso y así sucesivamente.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obtener más información sobre las barras de colaboración de las cuentas de recursos de Microsoft 365, consulte [crear una cuenta de recursos mediante el centro de administración de microsoft 365](resource-account-ui.md).

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si desea realizar o recibir llamadas telefónicas externas e identificar los requisitos de licencias de las cuentas de recursos.</li></ul>|
| ![Un icono que muestra los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Preparar cuentas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuración e implementación

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

- Aprovisionamiento de cuentas de recursos
- Implementación de dispositivos
- Barras de colaboración para la aplicación Microsoft Teams y configuración de dispositivos periféricos
-  Pruebas
- Administración de activos

### <a name="account-provisioning"></a>Aprovisionamiento de la cuenta

Si tiene previsto usar cuentas de recursos de 365 de Microsoft para permitir que los usuarios puedan usar las barras de colaboración, siga las instrucciones de [crear una cuenta de recursos con el centro de administración de microsoft 365](resource-account-ui.md) para crear una cuenta de recursos de Microsoft 365 para cada barra de colaboración que necesite. Aquí también tendrá que agregar una licencia de sala de reuniones a la cuenta de recursos y, si desea realizar o recibir llamadas a o desde números de teléfono externos, un plan de llamadas o una licencia de voz empresarial si su organización no está usando un enrutamiento directo.

Si desea asignar barras de colaboración a usuarios individuales para su uso privado, no necesita configurar cuentas adicionales. Los usuarios pueden iniciar sesión en barras de colaboración con sus cuentas personales.

> [!TIP]
> Haga que los nombres para mostrar de las cuentas de recursos de Microsoft 365 sean descriptivos y fáciles de comprender. Estos son los nombres que los usuarios verán al buscar y agregar barras de colaboración para Microsoft Teams a reuniones. Puede usar una Convención como *Site* - *el nombre de sala*de sitio (*capacidad máxima*de la sala), por lo que, por ejemplo Curie, un salón de reunión de 4 personas en Londres, podría tener el nombre para mostrar Lon-Curie (4).

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la Convención de nomenclatura para las cuentas de recursos dedicadas.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>|
| ![Un icono que muestra los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comience a planificar la implementación del dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implementación de dispositivos

A continuación, debe crear su plan para entregar los dispositivos y sus dispositivos periféricos asignados a sus salas y, después, proceder con la instalación y la configuración.

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir quién administrará la implementación sitio a sitio.</li><li> Identifique los recursos que instalarán las barras de colaboración de Microsoft Teams en el sitio y lleven a cabo la configuración y las pruebas.</li></ul>|
| ![Un icono que muestra los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Inicie las pruebas del dispositivo.</li></ul>|

### <a name="testing"></a> Pruebas

Después de implementar las barras de colaboración de Microsoft Teams, debe probarlas. Inicie sesión en el dispositivo y compruebe que las capacidades previstas estén funcionando en el dispositivo implementado. Le recomendamos que compruebe que los dispositivos aparecen en la sección barras de **colaboración** en la pestaña **dispositivos** del centro de administración de Microsoft Teams. También es importante que haga una serie de llamadas y reuniones de prueba para comprobar la calidad y el rendimiento.

Recomendamos que, como parte de la implementación general de Microsoft Teams, configure archivos de creación para el panel de calidad de llamadas (CQD), tendencias de calidad del monitor y participe en el proceso de revisión de la calidad de la experiencia. Para obtener más información, consulta la [Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide).

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, deseará actualizar el registro de activos con el nombre del salón, la cuenta de recursos con sesión iniciada y los dispositivos periféricos asignados.

## <a name="related-topics"></a>Temas relacionados

[Configurar cuentas para las barras de colaboración de Microsoft Teams mediante el centro de administración de Microsoft Teams](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
