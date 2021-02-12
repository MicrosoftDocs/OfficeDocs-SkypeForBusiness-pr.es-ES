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
description: Lea este artículo para obtener información sobre cómo implementar barras de colaboración para Microsoft Teams.
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962911"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Implementar barras de colaboración para Microsoft Teams

La implementación de las barras de colaboración de Microsoft Teams se puede dividir en las siguientes fases:

- **Disponibilidad del sitio** Confirme que las ubicaciones de implementación (salas) cumplen los requisitos de implementación.
- **Disponibilidad del servicio** Crear cuentas de recursos y asignarlas a los dispositivos (consulte Crear una cuenta de recursos [mediante el Centro de administración de Microsoft 365).](resource-account-ui.md) Aunque recomendamos usar una licencia de sala dedicada, una cuenta de usuario final con licencia adecuada también puede iniciar sesión en barras de colaboración.
- **Configuración e implementación** Configure barras de colaboración en salas y conecte los dispositivos periféricos que necesite (consulte la documentación del fabricante sobre las barras de colaboración).

Para administrar las barras de colaboración, debe ser administrador global, administrador del servicio de Teams o administrador de dispositivos de Teams. Para obtener más información sobre los roles de administrador, [consulte Usar roles de administrador de Microsoft Teams para administrar Teams.](../using-admin-roles.md)

## <a name="site-readiness"></a>Disponibilidad del sitio

Mientras los dispositivos ordenados se entregan a la organización, trabaje con sus equipos de redes, instalaciones y audio visual para asegurarse de que se cumplen los requisitos de implementación y que cada sitio y sala está preparado en términos de potencia, redes y pantalla.

Nuestras recomendaciones para sitios de barras de colaboración son:

- Salas de hasta 4 personas en tamaño
- Cuentas de recursos dedicadas
- Pantallas táctiles
- Cableado Ethernet
- Calidad de servicio (QoS) habilitada en la red para los medios de Microsoft Teams

Para las consideraciones de instalación física, consulte la documentación del fabricante y, si tiene una, aproveche la experiencia de su equipo de audio visual antes de instalar y montar pantallas y ejecutar el cableado.

> [!TIP]
> Asegúrese de comprobar Preparar la red para [Teams](../prepare-network.md) para planear el ancho de banda y evaluar la idoneidad de su red para el tráfico en tiempo real.
>
> No se recomienda colocar servidores proxy entre dispositivos Teams e Internet. Para obtener más información sobre los servidores proxy y Teams, consulte [Servidores proxy para Teams.](../proxy-servers-for-skype-for-business-online.md)

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que los sitios cumplen los requisitos de disponibilidad del sitio para las barras de colaboración de Microsoft Teams.</li><li>Confirme que ha proporcionado ancho de banda suficiente para cada sitio.</li></ul>|
| ![Un icono que muestra los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear la configuración y la implementación de la barra de colaboración.</li></ul>|

## <a name="service-readiness"></a>Preparación del servicio

Antes de implementar las barras de colaboración, debe decidir si usarán cuentas de recursos de Microsoft 365, cuentas de usuario final o una combinación de ambos. Las cuentas de recursos de Microsoft 365 son cuentas de buzón y de Teams que están dedicadas a recursos específicos, como una sala, proyector, entre otras. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones mediante las reglas que defina cuando se crean. A menos que una barra de colaboración esté dedicada a una persona específica para su uso privado, se recomienda configurar una cuenta de recursos de Microsoft 365 para ella.

### <a name="using-a-resource-account"></a>Usar una cuenta de recursos

Si decide configurar una cuenta de recursos de Microsoft 365, tendrá que comprar una licencia de Sala de reuniones para ella. La licencia de sala de reuniones incluye un buzón de recursos que permite a los usuarios de su organización reservar la sala de reuniones a través de Outlook o Teams. La licencia también habilita las videoconferencias y audioconferencias y el uso compartido de la pantalla entre los participantes de la reunión.

Si necesita recibir o realizar llamadas a un número de teléfono externo, es posible que necesite una licencia de plan de llamadas o del complemento Microsoft 365 Business [Voice.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business) Si ha habilitado el enrutamiento directo en su organización, solo necesita la SKU de la sala de reuniones.

Cuando crea una cuenta de recurso, puede elegir si quiere permitir que la cuenta acepte o rechace automáticamente las solicitudes de reunión, permita reuniones periódicas, especifique con qué antelación las personas pueden reservar el recurso, y así sucesivamente.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obtener más información sobre las barras de colaboración de las cuentas de recursos de Microsoft 365, vea Crear una cuenta de recurso mediante el Centro de administración [de Microsoft 365.](resource-account-ui.md)

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si desea realizar o recibir llamadas telefónicas externas e identificar los requisitos de licencia para sus cuentas de recursos.</li></ul>|
| ![Un icono que muestra los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Preparar cuentas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuración e implementación

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

- Aprovisionamiento de cuentas de recursos
- Implementación de dispositivos
- Barras de colaboración para la aplicación Microsoft Teams y la configuración del dispositivo periférico
-  Pruebas
- Administración de activos

### <a name="account-provisioning"></a>Aprovisionamiento de cuenta

Si tiene previsto usar cuentas de recursos de Microsoft 365 para permitir que los usuarios reserven barras de colaboración, siga las instrucciones de Crear una cuenta de recurso mediante el Centro de administración de [Microsoft 365](resource-account-ui.md) para crear una cuenta de recursos de Microsoft 365 para cada barra de colaboración que necesite una. Aquí también es donde deberá agregar una licencia de sala de reuniones a la cuenta del recurso y, si desea realizar o recibir llamadas a o desde números de teléfono externos, un plan de llamadas o una licencia de Business Voice si su organización no está usando enrutamiento directo.

Si desea asignar barras de colaboración a usuarios individuales para su uso privado, no es necesario configurar ninguna cuenta adicional. Los usuarios pueden iniciar sesión en barras de colaboración con sus cuentas personales.

> [!TIP]
> Haga que los nombres para mostrar de las cuentas de recursos de Microsoft 365 sea descriptivos y fáciles de entender. Estos son los nombres que verán los usuarios al buscar y agregar barras de colaboración de Microsoft Teams a las reuniones. Podría usar una convención como el nombre de la sala del sitio (capacidad máxima de la sala), por lo que, por ejemplo, Curie, una sala de reuniones para 4 personas en Londres, podría tener el nombre para mostrar - LON-CURIE(4).

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura para sus cuentas de recursos dedicadas.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>|
| ![Un icono que muestra los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear la implementación del dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implementación de dispositivos

A continuación, debe crear su plan para entregar los dispositivos y sus dispositivos periféricos asignados a sus salas y, después, continuar con la instalación y configuración.

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará la implementación de sitio por sitio.</li><li> Identifique los recursos que instalarán las barras de colaboración de Microsoft Teams en el sitio y realicen la configuración y las pruebas.</li></ul>|
| ![Un icono que muestra los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Iniciar pruebas de dispositivo.</li></ul>|

### <a name="testing"></a> Pruebas

Una vez que se hayan implementado las barras de colaboración de Microsoft Teams, debería probarlos. Inicie sesión en el dispositivo y compruebe que las capacidades esperadas estén funcionando en el dispositivo implementado. Se recomienda comprobar que los dispositivos aparecen  en la  sección Barras de colaboración de la pestaña Dispositivos del Centro de administración de Microsoft Teams. También es importante que realice varias llamadas de prueba y reuniones para comprobar la calidad y el rendimiento.

Le recomendamos que, como parte de la implementación general de Microsoft Teams, configure la creación de archivos para el panel de calidad de llamadas, supervisar tendencias de calidad y participar en el proceso de revisión de la calidad de la experiencia. Para obtener más información, vea la [Guía de revisión de la calidad de la experiencia.](https://aka.ms/qerguide)

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, tendrá que actualizar el registro de activos con el nombre del salón, la cuenta de recursos con la sesión firmada y los dispositivos periféricos asignados.

## <a name="related-topics"></a>Temas relacionados

[Configurar cuentas para las barras de colaboración de Microsoft Teams con el Centro de administración de Microsoft Teams](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
