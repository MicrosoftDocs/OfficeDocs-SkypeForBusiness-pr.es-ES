---
title: 'Lync Server 2013: Implementación de tareas para el control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63c9cba56ccedf3559b1e9f1da1ee58cc03e195
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Implementación de tareas para el control remoto de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

En este tema se describen las tareas de implementación que debe realizar para habilitar el control remoto de llamadas para los usuarios de su entorno de Lync Server.

<div>


> [!NOTE]  
> Si va a migrar usuarios previamente habilitados para el control remoto de llamadas en Microsoft Office Communicator 2007 R2, debe realizar una tarea de implementación adicional antes de comenzar a realizar las tareas de implementación del control de llamadas remotas que se describen en este tema. Durante el proceso de migración a Lync Server, las entradas de aplicaciones de confianza (antes conocidas como <EM>entradas de host autorizado</EM>) deben quitarse con las herramientas administrativas de Office Communications Server 2007 R2, según corresponda.<BR>Para obtener más información sobre cómo quitar los hosts autorizados, vea <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">quitar un host heredado autorizado en Lync Server 2013 (opcional)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Paso 1: instalar y configurar la puerta de enlace SIP/CSTA para comunicarse con su PBX

Debe instalar al menos una puerta de enlace SIP/CSTA que pueda conectarse a Lync Server y a la central de conmutación (PBX) existente en su entorno para proporcionar características de control de llamadas remotas a sus usuarios. Una puerta de enlace SIP/CSTA es una puerta de enlace entre SIP y una aplicación de telecomunicaciones compatible con el equipo (CSTA). Independientemente de si instala varias puertas de enlace o solo una, cada usuario puede configurarse con una sola puerta de enlace o PBX. Si su PBX existente no tiene una interfaz SIP/CSTA, asegúrese de implementar una puerta de enlace SIP/CSTA que admita el sistema PBX, incluida la compatibilidad de los protocolos de señalización específicos de PBX de terceros proveedores. Para obtener más información sobre las capacidades, consulte a cada proveedor directamente.

Cuando esté listo para implementar una puerta de enlace SIP/CSTA que pueda integrarse con Lync Server para el control remoto de llamadas, consulte también con el proveedor de la puerta de enlace o la documentación de la puerta de enlace del proveedor en relación con la sintaxis requerida por la puerta de enlace para la siguiente información:

  - URI de servidor de línea de la puerta de enlace

  - URI de línea para los usuarios que se asignarán a la puerta de enlace

La configuración anterior se necesita durante la configuración del usuario y debe especificarse como lo esperaba la puerta de enlace para enrutar y conectarse a la PBX correctamente.

Puede consultar a los proveedores en el sitio web del programa de interoperabilidad abierto [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)de comunicaciones unificadas de Microsoft en.

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Paso 2: configurar Lync Server para enrutar las solicitudes de CSTA a la puerta de enlace SIP/CSTA

Debe crear rutas estáticas en los grupos de servidores de Lync para la dirección de destino (URI de servidor) de todas las puertas de enlace SIP/CSTA de su implementación a las que desea enrutar solicitudes de control de llamadas remotas. También debe crear una entrada de aplicación de confianza que corresponda a cada dirección de destino. Al designar la puerta de enlace como aplicación de confianza, se le otorga el estado de confianza para ejecutarse como parte del entorno de Lync Server, aunque la haya desarrollado un tercero (y ejecuta lo que se conoce como *servicio externo* porque es un servicio que no es un parte integrada del producto). Por último, si Lync Server se conecta a la puerta de enlace SIP/CSTA con una conexión de protocolo de control de transmisión (TCP) en lugar de una conexión de seguridad de nivel de transporte (TLS), también debe definir la dirección IP de la puerta de enlace con el generador de topologías.

Para obtener detalles sobre la configuración de rutas estáticas, vea [configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Para obtener más información sobre cómo configurar entradas de aplicaciones de confianza, vea [configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Para obtener más información sobre cómo definir una dirección IP de puerta de enlace SIP/CSTA en el generador de topología, consulte [definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Paso 3: configurar los usuarios de Lync para el control remoto de llamadas

Una vez que los usuarios se hayan habilitado para Lync Server, puede usar el panel de control de Lync Server o el shell de administración de Lync Server para habilitarlos para el control remoto de llamadas. Durante este paso de implementación, se asigna a cada usuario un URI de servidor y un URI de línea. El URI del servidor de líneas es el URI SIP de la puerta de enlace SIP/CSTA que tiene previsto asignar al usuario. El URI de línea es el número de teléfono único asignado al usuario.

Para más información sobre cómo configurar usuarios para el control remoto de llamadas, vea [Habilitar usuarios de Lync para el control remoto de llamadas en Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Paso 4: definir las reglas de normalización de números de teléfono de Lync Server

En los escenarios de control remoto de llamadas, Lync Server usa reglas de normalización de números de teléfono para convertir los números de teléfono que recibe de la puerta de enlace SIP/CSTA al formato E. 164. Los números de teléfono deben estar en este formato estandarizado para que determinadas características de control remoto de llamadas funcionen correctamente. El control remoto de llamadas usa las mismas reglas de normalización de números de teléfono que configure para la normalización de números de teléfono del servicio de libreta de direcciones, que son diferentes de las reglas de normalización de números de teléfono usadas para telefonía IP empresarial.

Para obtener detalles sobre cómo el control remoto de llamadas usa reglas de normalización de números de teléfono, consulte [control remoto de llamadas y normalización de números de teléfono en Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Para obtener más información sobre las reglas de normalización de números de teléfono para el servicio de libreta de direcciones, consulte el tema sobre cómo [administrar el servicio de libreta de direcciones en Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) en la documentación de operaciones.

</div>

</div>

<span> </span>

</div>

</div>

</div>

