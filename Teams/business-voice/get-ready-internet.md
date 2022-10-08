---
title: Comprobar la conexión a Internet para Teams Phone System
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Comprobar que Internet está listo para Teams Phone System
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 7cef6f8b9a3bfa6aa99fe342f8d1abf66f7c6594
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480940"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>Comprobar la conexión a Internet para Teams Phone System

Teams Phone System es la tecnología de Microsoft para habilitar las capacidades telefónicas en Microsoft Teams con la nube de Microsoft 365. Todos los dispositivos que usan Microsoft Teams y Phone System necesitan una conexión a Internet.

Para obtener la mejor experiencia del sistema telefónico, necesitas una conexión a Internet de banda ancha que admita el número máximo de llamadas telefónicas que tu organización puede realizar en cualquier momento. También debe asegurarse de que los equipos de su red pueden llegar a los servicios de Microsoft 365.

## <a name="check-your-internet-connection-speed"></a>Comprobar la velocidad de la conexión a Internet

Este artículo ayuda a determinar si la conexión a Internet es lo suficientemente rápida para el número de personas que necesitan realizar llamadas telefónicas. Proporcionará información sobre su organización y obtendrá un informe que muestra la cantidad de conexión a Internet que usarán Teams y Sistema telefónico.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Recopilar información sobre la conexión a Internet y los usuarios

Antes de empezar, necesita la siguiente información:

* La velocidad de la conexión a Internet
* ¿Cuántas personas usarán el sistema telefónico principalmente desde la oficina?
* ¿Cuántas personas usarán el sistema telefónico principalmente desde una ubicación remota, como una oficina doméstica?

### <a name="enter-your-information-into-the-network-planner"></a>Escriba su información en el planificador de red

Siga estos pasos:

1. En un explorador, vaya a [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). Inicie sesión con una cuenta que tenga permisos de Administrador global. La cuenta que usó para registrarse en Microsoft 365 tiene estos permisos.
2. Abra **Planificación** y seleccione **Planeamiento de red**.
3. En **Planes de red**, seleccione **Agregar**. Escriba un nombre para su plan y después, seleccione **Aplicar**.
4. Seleccione el nombre de su plan de red.
5. En la página siguiente, seleccione **Agregar un sitio de red** en la pestaña **Sitios de red**.
6. Rellene los campos **Nombre del sitio** de red, **Usuarios de** red e **Capacidad de vínculo de Internet** y, a continuación, seleccione **Guardar**. Deje en blanco los otros campos en esta pantalla y no active las opciones **ExpressRoute** o **Conectado a WAN**.
7. En la pestaña **Informe**, seleccione **Iniciar un informe**.
8. Escriba un **nombre de informe** y el número de **usuarios de red** (**Office** y **Remoto**) y, a continuación, seleccione **Generar informe** para crear un informe que muestre los requisitos de ancho de banda para Teams. Le indicaremos cómo leer el informe en la siguiente sección.

### <a name="find-your-minimum-internet-connection-speed"></a>Buscar la velocidad mínima de conexión a Internet

Al seleccionar **Generar informe**, Microsoft 365 crea un informe.

En la columna **Impacto** y en la fila **Office 365**, este número muestra la cantidad de conexión a Internet que usarán Teams y Sistema telefónico. Te recomendamos que este número no sea superior al 30 % de la velocidad total de conexión a Internet. Por ejemplo, si la conexión a Internet es *de 60 Mbps*, Teams y Sistema telefónico no deberían usar más de *18 Mbps*.

Use esta ecuación para determinar la velocidad de conexión a Internet mínima: <*Número de impacto> / 0,3*.  

Supongamos que el número de impacto es *4,6875 Mbps*. El cálculo para encontrar la velocidad mínima de conexión a Internet sería *4,6875 / 0,3 = 15,6*. En este caso, la velocidad de la conexión a Internet debe ser al menos *15.6 Mbps*.

Si Teams y Sistema telefónico usarán más del 30 % de la velocidad total de la conexión a Internet, el número de **impacto** aparecerá en rojo. En ese caso, es posible que tengas que actualizar la conexión a Internet.

![Advertencia de velocidad de conexión.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> El impacto en el ancho de banda proporcionado por Network Planner es solo una estimación. Se recomienda usar el [panel de calidad de llamadas](../cqd-what-is-call-quality-dashboard.md) para supervisar activamente la experiencia del usuario en las llamadas de audio y vídeo con Microsoft Teams dentro de su organización.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Asegúrese de que los equipos y dispositivos de su red puedan conectarse a Microsoft 365

Los equipos y dispositivos que usan Phone System deben usar puertos de red específicos para comunicarse con los servicios de Microsoft 365. Estos puertos son esencialmente puertas a través de las cuales los dispositivos se comunican entre sí a través de una red o de Internet. El firewall necesita permitir que los dispositivos de la red lleguen a Microsoft 365 mediante los siguientes puertos de red de *salida*:

* **Puertos TCP** 80 y 443
* **Puertos UDP** 3478, 3479, 3480 y 3481

La forma más sencilla de comprobar si el firewall permite la comunicación en estos puertos de red es realizar una prueba de conectividad con la [herramienta de conectividad de red de Microsoft 365](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) desde la ubicación de la oficina que desea probar. Después de completar la prueba, comprueba los resultados y las recomendaciones.
