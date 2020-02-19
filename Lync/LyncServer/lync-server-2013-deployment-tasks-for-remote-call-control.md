---
title: 'Lync Server 2013: tareas de implementación para el control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1549cb2f71e5f6f0ab1d16907d5e83765780cca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Tareas de implementación para el control remoto de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

En este tema se describen las tareas de implementación que debe realizar para habilitar el control remoto de llamadas para los usuarios de su entorno de Lync Server.

<div>


> [!NOTE]  
> Si va a migrar usuarios habilitados previamente para control remoto de llamadas en Microsoft Office Communicator 2007 R2, debe realizar una tarea de implementación adicional antes de comenzar a realizar las tareas de implementación del control remoto de llamadas descritas en este tema. Durante el proceso de migración a Lync Server, las entradas de las aplicaciones de confianza (antes conocidas como <EM>entradas de host autorizadas</EM>) deben quitarse con las herramientas administrativas de Office Communications Server 2007 R2, según corresponda.<BR>Para obtener información detallada sobre cómo quitar hosts autorizados, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a Legacy host Authorized host in Lync Server 2013 (optional)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Paso 1: Instalar y configurar la puerta de enlace SIP/CSTA para comunicarse con la central de conmutación

Debe instalar al menos una puerta de enlace SIP/CSTA que pueda conectarse a Lync Server y a la central de conmutación (PBX) existente en su entorno para proporcionar características de control remoto de llamadas a los usuarios. Una puerta de enlace SIP/CSTA es una puerta de enlace entre SIP y la CSTA (aplicación de telecomunicaciones para equipo). Independientemente del número de puertas de enlace que se hayan instalado, todos los usuarios se pueden configurar con tan solo una puerta de enlace o PBX. En caso de que la PBX existente carezca de una interfaz de SIP/CSTA, asegúrese de que implementa una puerta de enlace SIP/CSTA que admita la PBX, así como los protocolos de señalización específicos del proveedor de la PBX en cuestión. Para obtener información detallada sobre estas funciones, acuda directamente al proveedor.

Cuando esté listo para implementar una puerta de enlace SIP/CSTA que pueda integrarse con Lync Server para el control remoto de llamadas, consulte también con el proveedor de la puerta de enlace o con la documentación de la puerta de enlace del proveedor para conocer la sintaxis requerida por la puerta de enlace para obtener la siguiente información:

  - URI del servidor de línea de la puerta de enlace

  - URI de línea de los usuarios que se van a asignar a la puerta de enlace.

La configuración anterior es necesaria durante la configuración de usuario y se debe especificar tal y como la puerta de enlace espera encontrarla para enrutar y conectarse a la PBX sin problemas.

Puede consultar a los proveedores en el sitio web del programa de interoperabilidad abierta [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309)de comunicaciones unificadas de Microsoft en.

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Paso 2: configurar Lync Server para enrutar las solicitudes CSTA a la puerta de enlace SIP/CSTA

Debe crear rutas estáticas en los grupos de Lync Server a la dirección de destino (URI de servidor) de todas las puertas de enlace SIP/CSTA de la implementación a la que desea enrutar las solicitudes de control de llamadas remotas. Asimismo, deberá crear una entrada de aplicación de confianza que se corresponda con cada dirección de destino. Al designar la puerta de enlace como una aplicación de confianza, se le concede el estado de confianza para que se ejecute como parte del entorno de Lync Server, aunque la haya desarrollado un tercero (y ejecute lo que se conoce como *servicio externo* porque es un servicio que no es una parte integrada del producto). Por último, si Lync Server se conectará a la puerta de enlace SIP/CSTA con una conexión de protocolo de control de transmisión (TCP) en lugar de con una conexión de seguridad de la capa de transporte (TLS), también debe definir la dirección IP de la puerta de enlace mediante el generador de topologías.

Para obtener más información sobre cómo configurar rutas estáticas, vea [configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Para obtener más información sobre cómo configurar entradas de aplicaciones de confianza, consulte [configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Para obtener más información sobre cómo definir una dirección IP de puerta de enlace SIP/CSTA en el generador de topologías, consulte [definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Paso 3: configurar los usuarios de Lync para el control remoto de llamadas

Una vez que se hayan habilitado los usuarios en Lync Server, puede usar el panel de control de Lync Server o el shell de administración de Lync Server para habilitarlos para el control remoto de llamadas. Durante este paso de implementación, se asigna a cada usuario un URI de línea de servidor y un URI de línea. El URI del servidor de línea es el URI del SIP de la puerta de enlace SIP/CSTA que va a asignar al usuario. El URI de línea es el número de teléfono único asignado al usuario.

Para más información sobre cómo configurar usuarios para el control remoto de llamadas, consulte [Habilitar usuarios de Lync para el control remoto de llamadas en Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Paso 4: Definir las reglas de normalización de números de teléfono de Lync Server

En los escenarios de control remoto de llamadas, Lync Server usa reglas de normalización de números de teléfono para convertir los números de teléfono que recibe de la puerta de enlace SIP/CSTA al formato E. 164. Los números de teléfono deben estar en este formato estandarizado para que determinadas características de control remoto de llamadas funcionen correctamente. El control remoto de llamadas usa las mismas reglas de normalización de números de teléfono que se configuran para la normalización de números de teléfono del servicio de libreta de direcciones, que son diferentes de las reglas de normalización de números de teléfono usadas para Enterprise Voice

Para obtener más información sobre cómo el control remoto de llamadas usa reglas de normalización de números de teléfono, consulte [control remoto de llamadas y normalización de números de teléfono en Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Para obtener más información sobre las reglas de normalización de números de teléfono para el servicio de libreta de direcciones, consulte el tema [Administración del servicio de libreta de direcciones en Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) en la documentación de operaciones.

</div>

</div>

<span> </span>

</div>

</div>

</div>

