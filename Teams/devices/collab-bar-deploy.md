---
title: Implementar Salas de Microsoft Teams en Android
ms.author: czawideh
author: cazawideh
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
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este artículo para obtener información sobre cómo implementar Salas de Microsoft Teams en Android.
ms.openlocfilehash: 7b37f03bdecf0bb6b1d3f3545d096836aa81b805
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514521"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Implementar Salas de Microsoft Teams en Android

La implementación Salas de Microsoft Teams en Android se puede dividir en las siguientes fases:

- **Preparación del sitio** Confirme que las ubicaciones de implementación (salas) cumplen los requisitos de implementación.
- **Preparación del servicio** Cree cuentas de recursos y asígnelas a los dispositivos ([vea Crear una cuenta de recursos con el Centro de administración de Microsoft 365](resource-account-ui.md)). Aunque se recomienda usar una licencia de sala dedicada, una cuenta de usuario final con licencia adecuada también puede iniciar sesión en Salas de Teams en Android.
- **Configuración e implementación** Configure Salas de Teams y conecte los dispositivos periféricos que necesita (consulte la documentación del fabricante para obtener más información).

Para administrar Salas de Teams, debe ser administrador global, administrador Teams servicio o administrador Teams dispositivo. Para obtener más información sobre los roles de administrador, vea [Usar Microsoft Teams de administrador para administrar Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Preparación del sitio

Mientras los dispositivos ordenados se entregan a su organización, trabaje con sus equipos de redes, instalaciones y audio visual para asegurarse de que se cumplen los requisitos de implementación y que cada sitio y salón está listo en términos de potencia, redes y pantalla.

Nuestras recomendaciones para los sitios de la barra de colaboración son:

- Salas de hasta 5 personas en tamaño
- Cuentas de recursos dedicadas
- Pantallas táctiles habilitadas
- Cableado Ethernet
- Calidad de servicio (QoS) habilitado en la red para Microsoft Teams multimedia

Para ver las consideraciones de instalación física, consulte la documentación del fabricante y, si tiene una, aproveche la experiencia de su equipo de audio visual antes de instalar y montar pantallas y ejecutar cableado.

> [!TIP]
> Asegúrese de consultar Preparar la [](../prepare-network.md) red para Teams para la planificación del ancho de banda y evaluar la idoneidad de su red para el tráfico en tiempo real.
>
> No se recomienda colocar servidores proxy entre Teams dispositivos e Internet. Para obtener más información sobre los servidores proxy y Teams, consulte [Servidores proxy Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Un icono que representa los puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que los sitios cumplen los requisitos de preparación del sitio para las barras de colaboración Microsoft Teams.</li><li>Confirme que ha proporcionado ancho de banda suficiente para cada sitio.</li></ul>|
| ![Un icono que muestra los pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Siguientes pasos|<ul><li>Empiece a planear la implementación y la configuración de la barra de colaboración.</li></ul>|

## <a name="service-readiness"></a>Preparación del servicio

Antes de implementar Salas de Teams, debe decidir si van a usar Microsoft 365 de recursos, cuentas de usuario final o una combinación de ambas. Microsoft 365 de recursos son cuentas de buzón y Teams que están dedicadas a recursos específicos, como un salón, un proyector, y así sucesivamente. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones mediante reglas que defina cuando se crean. A menos Salas de Teams esté dedicado a una persona específica para su uso privado, se recomienda configurar una Microsoft 365 de recursos para ella.

### <a name="using-a-resource-account"></a>Usar una cuenta de recursos

Si decide configurar una cuenta de Microsoft 365 de recursos, tendrá que comprar una Sala de reuniones licencia para ella. La Sala de reuniones incluye un buzón de recursos que permite a los usuarios de su organización reservar la sala de reuniones a través de Outlook o Teams. La licencia también permite videoconferencias y audioconferencias y uso compartido de pantalla entre los participantes de la reunión.

Si necesita recibir o realizar llamadas a o desde un número de teléfono externo, es posible que necesite un plan de llamadas o una licencia de Microsoft 365 Business Voice [complemento](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Si tiene enrutamiento directo habilitado en su organización, solo necesita la SKU Sala de reuniones usuario.

Al crear una cuenta de recursos, puede elegir si quiere permitir que la cuenta acepte o rechace automáticamente las solicitudes de reunión, permita reuniones periódicas, especifique con qué antelación los usuarios pueden reservar el recurso, y así sucesivamente.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obtener más información sobre Microsoft 365 de recursos, vea [Crear una cuenta de recursos con el Centro de administración de Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Un icono que representa los puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si desea realizar o recibir llamadas telefónicas externas e identificar los requisitos de licencia para sus cuentas de recursos.</li></ul>|
| ![Un icono que muestra los pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Siguientes pasos|<ul><li>Preparar cuentas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuración e implementación

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

- Aprovisionamiento de cuentas de recursos
- Implementación de dispositivos
- Salas de Teams de aplicaciones y dispositivos periféricos
-  Pruebas
- Administración de activos

### <a name="account-provisioning"></a>Aprovisionamiento de cuentas

Si planea usar cuentas de recursos Microsoft 365 para permitir que los usuarios reserven barras de colaboración, siga las instrucciones de Crear una cuenta de recursos con el Centro de administración de Microsoft 365 para crear una cuenta de recursos de [Microsoft 365](resource-account-ui.md) para cada barra de colaboración que necesite una. Aquí también es donde tendrá que agregar una licencia de Sala de reuniones a la cuenta de recursos y, si desea realizar o recibir llamadas a o desde números de teléfono externos, una licencia de Plan de llamadas o Voz empresarial si su organización no usa enrutamiento directo.

Si desea asignar Salas de Teams usuarios individuales para su uso privado, no es necesario configurar cuentas adicionales. Los usuarios pueden iniciar sesión en barras de colaboración con sus cuentas personales.

> [!TIP]
> Haga que los nombres para mostrar de Microsoft 365 cuentas de recursos sea descriptivo y fácil de entender. Estos son los nombres que verán los usuarios al buscar y agregar Salas de Teams a las reuniones. Puede usar una convención como *Nombre*- de sala de *sitio(Capacidad* máxima de la *sala), por* lo que, por ejemplo, Curie, una sala de reuniones de 4 personas en Londres, podría tener el nombre para mostrar LON-CURIE(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Un icono que representa los puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura para sus cuentas de recursos dedicadas.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>|
| ![Un icono que muestra los pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Siguientes pasos|<ul><li>Empiece a planear la implementación del dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implementación de dispositivos

A continuación, debe crear su plan para entregar los dispositivos y sus dispositivos periféricos asignados a sus salas y, después, continuar con la instalación y la configuración.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Un icono que representa los puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará la implementación de sitio por sitio.</li><li> Identifique los recursos que instalarán Salas de Teams en el sitio y realice la configuración y las pruebas.</li></ul>|
| ![Un icono que muestra los pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Siguientes pasos|<ul><li>Iniciar pruebas de dispositivos.</li></ul>|

### <a name="testing"></a> Pruebas

Después de implementar Salas de Teams, debe probarlos. Inicie sesión para Salas de Teams y compruebe que las capacidades esperadas funcionan. Le recomendamos que compruebe que aparecen en la sección Barras de colaboración de la pestaña Teams **dispositivos** de Microsoft Teams centro de administración. También es importante que realice una serie de llamadas de prueba y reuniones para comprobar la calidad y el rendimiento.

Le recomendamos que, como parte de la implementación general de Microsoft Teams, configure la creación de archivos para el Panel de calidad de llamadas (CQD), supervise las tendencias de calidad y participe en el proceso de revisión de calidad de la experiencia. Para obtener más información, consulte la [Guía de revisión de calidad de la experiencia](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, querrá actualizar el registro de activos con el nombre del salón, la cuenta de recursos que ha iniciado sesión y los dispositivos periféricos asignados.

## <a name="related-topics"></a>Temas relacionados

[Crear cuentas de recursos para salas y dispositivos Teams compartidos](../rooms/with-office-365.md)