---
title: Implementar Salas de Microsoft Teams en Android
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este artículo para obtener información sobre cómo implementar Salas de Microsoft Teams en Android.
ms.openlocfilehash: f5f49a7e461153d24837d28d7160a475e4992eba
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267815"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Implementar Salas de Microsoft Teams en Android

La implementación de Salas de Microsoft Teams en Android se puede dividir en las siguientes fases:

- **Disponibilidad del sitio** Confirme que las ubicaciones de implementación (salas) cumplen los requisitos de implementación.
- **Preparación del servicio** Cree cuentas de recursos y asígnelas a los dispositivos ([consulte Crear una cuenta de recursos con la Centro de administración de Microsoft 365](resource-account-ui.md)). Aunque recomendamos usar una licencia de sala dedicada, una cuenta de usuario final con licencia adecuada también puede iniciar sesión en Salas de Teams en Android.
- **Configuración e implementación** Configura Salas de Teams y conecta los dispositivos periféricos que necesitas (consulta la documentación del fabricante para obtener más información).

Para administrar Salas de Teams, debe ser administrador global, administrador de servicios de Teams o administrador de dispositivos de Teams. Para obtener más información sobre los roles de administrador, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Disponibilidad del sitio

Mientras se entregan los dispositivos ordenados a su organización, trabaje con sus equipos de redes, instalaciones y audiovisuales para asegurarse de que se cumplen los requisitos de implementación y de que cada sitio y sala está listo en términos de potencia, redes y pantalla.

Nuestras recomendaciones para los sitios de la barra de colaboración son:

- Habitaciones de hasta 5 personas de tamaño
- Cuentas de recursos dedicados
- Pantallas táctiles
- Cableado Ethernet
- Calidad de servicio (QoS) habilitada en la red para medios de Microsoft Teams

Para consideraciones de instalación física, consulta la documentación del fabricante y, si dispones de una, aprovecha la experiencia de tu equipo audiovisual antes de instalar y montar pantallas y ejecutar cableado.

> [!TIP]
> Asegúrese de consultar [Preparar la red para Teams para](../prepare-network.md) planear el ancho de banda y evaluar la idoneidad de la red para el tráfico en tiempo real.
>
> No se recomienda colocar servidores proxy entre dispositivos Teams e Internet. Para obtener más información sobre los servidores proxy y Teams, consulte [Servidores proxy para Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Un icono que representa los puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que los sitios cumplen los requisitos de preparación del sitio para las barras de colaboración para Microsoft Teams.</li><li>Confirme que ha proporcionado ancho de banda suficiente para cada sitio.</li></ul>|
| ![Un icono que muestra los pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comience a planear la implementación y configuración de la barra de colaboración.</li></ul>|

## <a name="service-readiness"></a>Preparación del servicio

Antes de implementar Salas de Teams, debe decidir si usarán cuentas de recursos de Microsoft 365, cuentas de usuario final o una mezcla de ambos. Las cuentas de recursos de Microsoft 365 son cuentas de buzón y de Teams dedicadas a recursos específicos, como una sala, un proyector, etc. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones con reglas que defina cuando se creen. A menos que Salas de Teams esté dedicado a una persona específica para su uso privado, le recomendamos que configure una cuenta de recursos de Microsoft 365 para ella.

### <a name="using-a-resource-account"></a>Usar una cuenta de recursos

Si decide configurar una cuenta de recursos de Microsoft 365, tendrá que comprar una licencia de Sala de reuniones para ella. La licencia de sala de reuniones incluye un buzón de recursos que permite a los usuarios de su organización reservar la sala de reuniones a través de Outlook o Teams. La licencia también permite la videoconferencia y audioconferencia y el uso compartido de la pantalla entre los participantes de la reunión.

Si necesita recibir o realizar llamadas a o desde un número de teléfono externo, es posible que necesite un Plan de llamadas o Microsoft 365 Business Voice [licencia complementaria](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Si tiene habilitado enrutamiento directo en su organización, solo necesita la SKU de la sala de reuniones.

Al crear una cuenta de recursos, puede elegir si desea permitir que la cuenta acepte o rechace automáticamente las convocatorias de reunión, permita reuniones periódicas, especifique con qué antelación los usuarios pueden reservar el recurso, etc.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obtener más información sobre las cuentas de recursos de Microsoft 365, vea [Crear una cuenta de recursos con la Centro de administración de Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Un icono que representa los puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si desea realizar o recibir llamadas telefónicas externas e identificar los requisitos de licencia para sus cuentas de recursos.</li></ul>|
| ![Un icono que muestra los pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Preparar cuentas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuración e implementación

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

- Aprovisionamiento de cuentas de recursos
- Implementación de dispositivos
- configuración de dispositivos periféricos y aplicaciones Salas de Teams
-  Pruebas
- Administración de activos

### <a name="account-provisioning"></a>Aprovisionamiento de cuentas

Si tiene previsto usar cuentas de recursos de Microsoft 365 para permitir que los usuarios reserven barras de colaboración, siga las instrucciones de [Crear una cuenta de recursos con la Centro de administración de Microsoft 365](resource-account-ui.md) para crear una cuenta de recursos de Microsoft 365 para cada barra de colaboración que necesite una. Aquí también es donde tendrá que agregar una licencia de Sala de reuniones a la cuenta de recursos y, si quiere realizar o recibir llamadas a números de teléfono externos o desde números de teléfono externos, un plan de llamadas o una licencia de Business Voice si su organización no usa enrutamiento directo.

Si desea asignar Salas de Teams a usuarios individuales para su uso privado, no es necesario configurar ninguna cuenta adicional. Los usuarios pueden iniciar sesión en las barras de colaboración con sus cuentas personales.

> [!TIP]
> Haga que los nombres para mostrar de sus cuentas de recursos de Microsoft 365 sean descriptivos y fáciles de entender. Estos son los nombres que verán los usuarios al buscar y agregar Salas de Teams a las reuniones. Puede usar una convención como *Nombre de la sala* del *sitio*-(*Capacidad máxima* de sala), de modo que, por ejemplo, Curie, una sala de reuniones de 4 personas en Londres, podría tener el nombre para mostrar LON-CURIE(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Un icono que representa los puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura para sus cuentas de recursos dedicadas.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>|
| ![Un icono que muestra los pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comienza a planear la implementación de tu dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implementación de dispositivos

A continuación, debe crear su plan para entregar los dispositivos y los dispositivos periféricos asignados a sus salas y, a continuación, proceder con la instalación y configuración.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Un icono que representa los puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará la implementación de sitio por sitio.</li><li> Identifique los recursos que instalarán Salas de Teams en el sitio y realice la configuración y las pruebas.</li></ul>|
| ![Un icono que muestra los pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Iniciar pruebas de dispositivos.</li></ul>|

### <a name="testing"></a> Pruebas

Después de implementar Salas de Teams, debe probarlos. Inicia sesión en Salas de Teams y comprueba que las capacidades esperadas funcionan. Le recomendamos que compruebe que aparecen en la sección Barras de **colaboración** en la pestaña **Dispositivos de Teams** del Centro de administración de Microsoft Teams. También es importante que realice una serie de llamadas de prueba y reuniones para comprobar la calidad y el rendimiento.

Le recomendamos que, como parte de la implementación general de Microsoft Teams, configure archivos de creación para el panel de calidad de llamadas, supervise las tendencias de calidad y participe en el proceso de revisión de la calidad de la experiencia. Para obtener más información, consulta la [Guía de revisión de calidad de la experiencia](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, querrá actualizar el registro de activos con el nombre del salón, la cuenta de recursos con sesión iniciada y los dispositivos periféricos asignados.

## <a name="related-topics"></a>Temas relacionados

[Crear cuentas de recursos para salas y dispositivos compartidos de Teams](../rooms/with-office-365.md)