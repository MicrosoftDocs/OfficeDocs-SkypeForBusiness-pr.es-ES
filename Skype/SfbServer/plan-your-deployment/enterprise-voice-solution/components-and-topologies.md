---
title: Componentes y topologías para el control de admisión de llamadas en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planificación del control de admisión de llamadas (CAC) si tiene una red MPLS, un tronco SIP o una puerta de enlace RTC o PBX de terceros. Se aplica a skype empresarial server Telefonía IP empresarial.
ms.openlocfilehash: e40525121020259a40f10d90cd79d70aaa749ac3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825850"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Componentes y topologías para el control de admisión de llamadas en Skype Empresarial

Planificación del control de admisión de llamadas (CAC) si tiene una red MPLS, un tronco SIP o una puerta de enlace RTC o PBX de terceros. Se aplica a skype empresarial server Telefonía IP empresarial.

Los temas de esta sección ofrecen información acerca de las consideraciones especiales para implementar el control de admisión de llamadas (CAC) con diversos tipos de topologías de red.

## <a name="call-admission-control-on-an-mpls-network"></a>Control de admisión de llamadas en una red MPLS

En una red de conmutación de etiquetas multiprotocolo (MPLS), todos los sitios se conectan mediante una malla completa. Es decir, todos los sitios se conectan directamente a la red troncal del proveedor del servicio de internet MPLS, y se proporciona ancho de banda a todos los sitios para que lo usen a través de un vínculo WAN a la nube MPLS. No existe ningún concentrador de red ni ningún sitio central que controle el enrutamiento IP. En la siguiente figura se muestra una red sencilla basada en la tecnología MPLS.

**Red MPLS de ejemplo**

![CAC con MPLS](../../media/CAC_MPLS_1.jpg)

Para implementar el control admisión de llamadas (CAC) en una red MPLS, debe crear una región de red que represente la nube MPLS y un sitio de red que represente cada uno de los sitios satélite MPLS. En la siguiente figura se muestra cómo deberán configurarse la región de red y los sitios de red para representar la red MPLS de ejemplo de la figura anterior. Los límites de ancho de banda generales y los límites de sesión de ancho de banda se basan en la capacidad del vínculo WAN desde el sitio de red hasta la región de red que representa la nube MPLS.

**Región de red y sitios de red para una red MPLS**

![Control de admisión de llamadas (CAC) con diagrama MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>Control de admisión de llamadas en un tronco SIP

Para implementar el control de admisión de llamadas (CAC) en un tronco SIP, debe crear un sitio de red para representar al proveedor de servicios de telefonía de Internet (ITSP). Para aplicar valores de directivas de ancho de banda al tronco SIP, debe crear una directiva entre el sitio de red de su empresa y el sitio de red que cree para representar al ITSP.

La siguiente ilustración muestra un ejemplo de implementación de CAC en un tronco SIP.

**Configuración de CAC en un tronco SIP**

![Diagrama de enlace troncal SIP de control de admisión de llamadas](../../media/CAC_SIP_trunk_1.jpg)

Para configurar el CAC en un tronco SIP, deberá realizar las siguientes tareas durante la implementación de CAC:

1. Cree un sitio de red para representar al ITSP. Asocie el sitio de red a una región de red adecuada y asigne un ancho de banda de cero para el audio y el vídeo de este sitio de red. Para ver más detalles, consulte [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) en la documentación sobre implementación.

    > [!NOTE]
    > Para el ITSP, no funciona esta configuración de sitio de red. Los valores de la directiva de ancho de banda se aplican, en realidad, en el paso 2.

2. Cree un vínculo entre sitios para el tronco SIP, usando los valores de los parámetros correspondientes al sitio que creó en el paso 1. Por ejemplo, use el nombre del sitio de red de su empresa como el valor del parámetro NetworkSiteID1 y el sitio de red ITSP como el valor del parámetro NetworkSiteID2. Para obtener más información, consulte Crear directivas entre sitios de red en [Skype Empresarial Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) en la documentación sobre implementación y [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).

3. Obtiene la dirección IP del punto de terminación de medios del controlador de borde de sesión (SCB) de tu ITSP. Agregue esa dirección IP con una máscara de subred de 32 al sitio de red que representa al ITSP. Para ver más detalles, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>Control de admisión de llamadas con una puerta de enlace RTC o PBX de terceros

En este tema se describen ejemplos de cómo se puede implementar el control de admisión de llamadas (CAC) en el vínculo entre la interfaz de puerta de enlace del servidor de mediación y una puerta de enlace de red telefónica conmutada (RTC) o central de conmutación (PBX) de terceros.

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Caso 1: Control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC

El CAC se puede implementar en el vínculo WAN desde la interfaz de puerta de enlace del servidor de mediación a una puerta de enlace RTC o PBX de terceros.

**Caso 1: Control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC**

![Caso 1: CAC entre la puerta de enlace RTC del servidor de mediación](../../media/CAC_gateways_1.jpg)

En este ejemplo, el control de admisión de llamadas se aplica entre el servidor de mediación y una puerta de enlace RTC. Si un usuario de cliente de Skype Empresarial en el sitio de red 1 hace una llamada RTC a través de la puerta de enlace RTC en el sitio de red 2, los medios fluyen a través del vínculo WAN. Por tanto, se llevan a cabo dos comprobaciones de control de admisión de llamadas para cada sesión RTC:

- Entre la aplicación cliente de Skype Empresarial y el servidor de mediación

- Entre el servidor de mediación y la puerta de enlace RTC

Esto funciona tanto para las llamadas RTC entrantes a un cliente en el Sitio de red 1 como para las llamadas RTC salientes desde una aplicación cliente en el Sitio de red 1.

> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezca la puerta de enlace RTC esté configurada y asociada con el Sitio de red 2.

> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.

> [!NOTE]
> Para ver más detalles, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Caso 2: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con punto de terminación de medios (MTP, Media Termination Point)

Esta configuración es similar a la del Caso 1. En ambos casos, el servidor de mediación sabe en qué dispositivo terminan los medios en el extremo opuesto del vínculo WAN, y la dirección IP de la puerta de enlace RTC o de la PBX que tiene el MTP está configurada en el servidor de mediación como siguiente salto.

**Caso 2: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con MTP**

![Caso 2: CAC entre PBX del servidor de mediación con MTP](../../media/CAC_gateways_2.jpg)

En este ejemplo, el control de admisión de llamadas se aplica entre el servidor de mediación y el MTP o la PBX. Si un usuario de cliente de Skype Empresarial en el sitio de red 1 hace una llamada RTC a través de la PBX/MTP ubicada en el sitio de red 2, los medios fluyen a través del vínculo WAN. Por tanto, se llevan a cabo dos comprobaciones de control de admisión de llamadas para cada sesión RTC:

- Entre la aplicación cliente de Skype Empresarial y el servidor de mediación

- Entre el servidor de mediación y la PBX o el MTP

Esto funciona tanto para las llamadas RTC entrantes a un cliente en el Sitio de red 1 como para las llamadas RTC salientes desde un cliente en el Sitio de red 1.

> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezca el MTP esté configurada y asociada con el Sitio de red 2.

> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.

> [!NOTE]
> Para ver más detalles, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Caso 3: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP

El Caso 3 es ligeramente diferente a los dos primeros casos. Si no hay ningún MTP en la PBX de terceros, en el caso de una solicitud de sesión saliente enviada a la PBX de terceros, el servidor de mediación no sabe dónde terminarán los medios en el límite de la PBX. En tal caso, los medios se transmiten directamente entre el servidor de mediación y el dispositivo del extremo de terceros.

**Caso 3: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP**

![Caso 3: CAC entre PBX del servidor de mediación sin MTP](../../media/CAC_gateways_3.jpg)

En este ejemplo, si un usuario de cliente de Skype Empresarial en el sitio de red 1 realiza una llamada a un usuario a través de la PBX, el servidor de mediación solo puede realizar comprobaciones de CAC en la parte de proxy (entre la aplicación cliente de Skype Empresarial y el servidor de mediación). Dado que el servidor de mediación no tiene información sobre el dispositivo del extremo, durante el proceso de solicitud de la sesión, no pueden realizarse comprobaciones de control de admisión de llamadas en el vínculo WAN (entre el servidor de mediación y el extremo de terceros) antes del establecimiento de llamada. Sin embargo, una vez establecida la sesión, el servidor de mediación facilita la cantidad de ancho de banda usada en el tronco.

Para las llamadas realizadas desde el extremo de terceros, la información sobre el dispositivo del extremo está disponible en el momento de la solicitud de la sesión y la comprobación de control de admisión de llamadas puede realizarse en ambas partes del servidor de mediación.

> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezca el dispositivo del extremo esté configurada y asociada con el Sitio de red 2.

> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.

> [!NOTE]
> Para ver más detalles, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).


