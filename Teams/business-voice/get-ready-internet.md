---
title: Comprobar la conexión a Internet
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653556"
---
# <a name="check-your-internet-connection"></a>Comprobar la conexión a Internet

Business Voice se encuentra en la nube con Microsoft 365. Todos los equipos y dispositivos que usan Microsoft Teams y Business Voice necesitan una conexión a Internet. Para obtener la mejor experiencia con Business Voice, necesita una conexión a Internet de banda ancha que sea compatible con el número de llamadas telefónicas que se espera que se realicen en un momento determinado. También tiene que asegurarse de que los equipos de la red pueden conectarse con los servidores de Microsoft 365.

Para seguir estos pasos, debe tener un espacio empresarial con una de las siguientes suscripciones:

* Office 365 Empresa Essentials
* Office 365 Empresa Premium
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 Empresa

No necesita una licencia de Business Voice para seguir estos pasos.

## <a name="check-your-internet-connection-speed"></a>Compruebe la velocidad de la conexión a Internet

Este artículo le ayudará a determinar si la conexión a Internet es lo suficientemente rápida para el número de personas que necesitan realizar llamadas telefónicas, hospedar videoconferencias, etc. Introducirá información acerca de su organización y recibirá un informe en el que se indicará la proporción de conexión a Internet que usarán Teams y Business Voice.

### <a name="get-information-about-your-internet-connection-and-users"></a>Obtener información sobre la conexión a Internet y los usuarios

Antes de empezar, debe averiguar la siguiente información:

* La velocidad de la conexión a Internet.
* El número de usuarios que usará Business Voice principalmente desde su oficina.
* La cantidad de personas que usará Business Voice principalmente desde una ubicación remota, por ejemplo, una oficina en casa.

### <a name="enter-your-information-into-the-network-planner"></a>Escriba su información en el Planeamiento de red

Esto es lo que tiene que hacer:

1. Abra un explorador, vaya a https://admin.teams.microsoft.com e inicie sesión con una cuenta que tenga permisos de administrador global. La cuenta que usó para registrarse en Office 365 tiene estos permisos.
1. Abra **Planificación** y, a continuación, seleccione **Planeamiento de red**.
1. En **Planes de red**, seleccione **Agregar**. Asigne un nombre a su plan y, después, seleccione **Aplicar**. El plan de red debe tener el siguiente aspecto:

    ![Pantalla principal de Planeamiento de red](../media/network-planner-main.png)
1. Haga clic en el nombre del plan de red (**Oficina principal** en la imagen anterior).
1. En la página siguiente, seleccione **Agregar un sitio de red** en la pestaña **Sitios de red**.
1. Rellene solo los campos que se muestran en la siguiente captura de pantalla y, a continuación, seleccione **Guardar**. Deje en blanco los otros campos de esta pantalla y no active las opciones **ExpressRoute** o **Conectado a WAN**.

    ![Información del sitio de Planeamiento de red](../media/network-planner-site-info.png)
1. En la pestaña **Informe**, seleccione **Iniciar un informe**.
1. Rellene la información siguiente y, a continuación, seleccione **Generar informe** para crear un informe que muestre los requisitos de ancho de banda para los Teams. En la siguiente sección se mostrará cómo leer el informe.

    ![Información del informe de Planeamiento de red](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>Averigüe cuál es la velocidad mínima de la conexión a Internet

Cuando selecciona **Generar informe**, Office 365 crea un informe similar a este:

![Detalles del informe de Planeamiento de red](../media/network-planner-report.png)

El número resaltado muestra qué proporción de su conexión a Internet usarán Teams y Business Voice. Se recomienda que este número no supere el 30 % de la velocidad total de conexión a Internet. Por ejemplo, si su conexión a Internet es 60 Mbps, Teams y Business Voice no deben ocupar más de 18 Mbps.

Para averiguar la velocidad de conexión a Internet mínima, haga este cálculo: `<highlighted number> / .3`. Si usa el número resaltado de la imagen anterior, el cálculo sería `4.6875 / .3 = 15.6`. Esto significa que la velocidad mínima de conexión a Internet debe ser de al menos 15,6 Mbps.

Si Teams y Business Voice van a usar más de un 30 % de la velocidad total de conexión a Internet, el número resaltado se mostrará en rojo. Si esto ocurre, es posible que tenga que actualizar la conexión a Internet.

![Advertencia de velocidad de conexión](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Asegúrese de que los equipos y dispositivos de su red puedan conectarse a Microsoft 365

Para funcionar correctamente, los equipos y dispositivos que desee usar con Business Voice necesitan comunicarse con servidores de Microsoft 365 que usen puertos de red específicos. Los puertos de red son, esencialmente, las puertas a través de las que los equipos y dispositivos pueden comunicarse entre sí por la red o por Internet. El firewall necesita permitir que equipos y dispositivos de la red lleguen a Microsoft 365 mediante los siguientes puertos de red de salida:

* **Puertos TCP** 80 y 443
* **Puertos UDP** 3478, 3479, 3480 y 3481

La forma más sencilla de comprobar si el firewall permite la comunicación en estos puertos de red es realizar una llamada de prueba con Teams. Para realizar una llamada de prueba, haga lo siguiente:

1. Vaya a https://aka.ms/getteams en un equipo de la red para instalar Teams. Asegúrese de que los altavoces y un micrófono estén conectados a este equipo.
2. Abra Teams e inicie sesión con una cuenta de Microsoft 365
3. En Teams, seleccione su imagen de perfil y, a continuación, **Configuración** > **Dispositivos**
4. Elija **Realizar una llamada de prueba** en **Dispositivos de audio**
5. Siga las indicaciones para dejar un mensaje y pedir que se lo reproduzcan

* Si la llamada se conecta y puede escuchar su mensaje grabado, el firewall está configurado correctamente.
* Si la llamada se conecta pero no oye las preguntas o el mensaje grabado, asegúrese de que el equipo y los parlantes estén configurados correctamente y que el equipo los haya detectado. Inténtelo de nuevo.
* Si la llamada no se conecta o si lo hace pero no escucha su mensaje grabado, es posible que tenga que actualizar el firewall para permitir los puertos de red enumerados anteriormente. Consulte la documentación del firewall para saber cómo permitir que los puertos de red lleguen a Internet o póngase en contacto con un especialista de TI para que le ayude.

Si es un profesional de TI y desea obtener más información sobre cómo preparar redes más grandes o de mayor complejidad para que sean compatibles con Business Voice, eche un vistazo a [Evaluar mi entorno](../3-envision-evaluate-my-environment.md). El artículo [Evaluar mi entorno](../3-envision-evaluate-my-environment.md) ofrece información adicional sobre los requisitos de ancho de banda, proxy y firewall, y también sobre cómo probar la red con la [Herramienta de evaluación de red](../3-envision-evaluate-my-environment.md#test-the-network).
