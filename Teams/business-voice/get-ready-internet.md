---
title: Comprueba si hay Teams Sistema telefónico
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Comprueba que internet está listo para Teams Sistema telefónico
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b165f540fe3c6280f1c6a7c2b4dec716a1fa611
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053099"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>Comprueba si hay Teams Sistema telefónico

Teams Sistema telefónico es la tecnología de Microsoft para habilitar las capacidades del teléfono dentro de Microsoft Teams usar la Microsoft 365 nube. Todos los dispositivos que Microsoft Teams y Sistema telefónico necesitan una conexión a Internet.

Para obtener la mejor Sistema telefónico, necesita una conexión a Internet de banda ancha que pueda admitir el número máximo de llamadas telefónicas que su organización puede realizar en cualquier momento. También debe asegurarse de que los equipos de su red pueden llegar a Microsoft 365 servicios.

## <a name="check-your-internet-connection-speed"></a>Comprobar la velocidad de conexión a Internet

Este artículo ayuda a determinar si la conexión a Internet es lo suficientemente rápida para el número de personas que necesitan realizar llamadas telefónicas. Proporcionará información sobre su organización y recuperará un informe que muestra la cantidad de su conexión a Internet que usarán Teams y Sistema telefónico.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Recopilar información sobre la conexión a Internet y los usuarios

Antes de empezar, necesita la siguiente información:

* La velocidad de la conexión a Internet
* ¿Cuántas personas usarán Sistema telefónico principalmente desde su oficina?
* ¿Cuántas personas usarán Sistema telefónico principalmente desde una ubicación remota, como una oficina en el hogar

### <a name="enter-your-information-into-the-network-planner"></a>Escriba su información en el planificador de red

Siga estos pasos:

1. En un explorador, vaya a [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). Inicie sesión con una cuenta que tenga permisos de Administrador global. La cuenta que usó para registrarse Microsoft 365 tiene estos permisos.
2. Abra **Planificación** y seleccione **Planeamiento de red**.
3. En **Planes de red**, seleccione **Agregar**. Escriba un nombre para su plan y después, seleccione **Aplicar**.
4. Seleccione el nombre de su plan de red.
5. En la página siguiente, seleccione **Agregar un sitio de red** en la pestaña **Sitios de red**.
6. Rellene los campos **Nombre de sitio de red****, Usuarios** de red y Capacidad del **vínculo a Internet** y, a continuación, **seleccione Guardar**. Deje en blanco los otros campos en esta pantalla y no active las opciones **ExpressRoute** o **Conectado a WAN**.
7. En la pestaña **Informe**, seleccione **Iniciar un informe**.
8. Escriba un nombre **de** informe y el número de usuarios de **red (** Office y **Remoto) y****, a** continuación, seleccione Generar informe para crear un informe que muestre los requisitos de ancho de banda Teams. Le informaremos cómo leer el informe en la sección siguiente.

### <a name="find-your-minimum-internet-connection-speed"></a>Buscar la velocidad mínima de conexión a Internet

Al seleccionar **Generar informe**, Microsoft 365 crea un informe.

En la **columna** Impacto y en la fila **Office 365**, este número muestra la cantidad de la conexión a Internet Teams y Sistema telefónico usarán. Se recomienda que este número no sea más del 30 por ciento de la velocidad total de conexión a Internet. Por ejemplo, si la conexión a Internet es *de 60 Mbps*, Teams y Sistema telefónico no deben usar más de *18 Mbps*.

Use esta ecuación para determinar la velocidad mínima de conexión a Internet: <*número de impacto> / 0,3*.  

Supongamos que el número de impacto es *4,6875 Mbps*. El cálculo para encontrar la velocidad mínima de conexión a Internet sería *4,6875 / 0,3 = 15,6*. En este caso, la velocidad de conexión a Internet debe ser de al menos *15,6 Mbps*.

Si Teams y Sistema telefónico usarán más del 30 por ciento de la velocidad total de conexión a Internet, el número de impacto aparecerá  en rojo. En ese caso, es posible que deba actualizar la conexión a Internet.

![Advertencia de velocidad de conexión.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> El impacto del ancho de banda proporcionado por Network Planner es solo una estimación. Se recomienda usar [el Panel de](../cqd-what-is-call-quality-dashboard.md) calidad de llamadas para supervisar de forma activa la experiencia del usuario para las llamadas de audio y videollamadas con Microsoft Teams dentro de su organización.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Asegúrese de que los equipos y dispositivos de su red puedan conectarse a Microsoft 365

Los equipos y dispositivos que usan Sistema telefónico deben usar puertos de red específicos para comunicarse con Microsoft 365 servicios. Estos puertos son básicamente puertas a través de las cuales los dispositivos se hablan entre sí a través de una red o Internet. El firewall necesita permitir que los dispositivos de la red lleguen a Microsoft 365 mediante los siguientes puertos de red de *salida*:

* **Puertos TCP** 80 y 443
* **Puertos UDP** 3478, 3479, 3480 y 3481

La forma más sencilla de comprobar si el firewall permite la comunicación en estos puertos de red es realizar una prueba [](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) de conectividad con la herramienta de conectividad de red Microsoft 365 desde la ubicación de la oficina que desea probar. Después de completar la prueba, compruebe los resultados y las recomendaciones.
