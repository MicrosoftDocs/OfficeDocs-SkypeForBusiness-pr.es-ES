---
title: 'Lync Server 2013: Implementación de tareas para el control remoto de llamadas'
TOCTitle: Implementación de tareas para el control remoto de llamadas
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48274629
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de tareas para el control remoto de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En este tema se describen las tareas de implementación que deben realizarse para habilitar el control remoto de llamadas para los usuarios del entorno de Lync Server.


> [!NOTE]
> En caso de que migre usuarios que ya tenían el control remoto de llamadas habilitado en Microsoft Office Communicator 2007 R2, es necesario realizar una tarea de implementación más antes de centrarse en las tareas de implementación de control remoto de llamadas descritas en este tema. Durante el proceso de migración a Lync Server, es necesario quitar las entradas de la aplicación de confianza (denominadas anteriormente <EM>entradas de host autorizado</EM> ), para lo cual se usan las herramientas administrativas de Office Communications Server 2007 R2, según proceda.<BR>Para más información detallada sobre cómo quitar hosts autorizados, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Quitar un host autorizado heredado en Lync Server 2013 (opcional)</A>.



## Paso 1: Instalar y configurar la puerta de enlace SIP/CSTA para comunicarse con la central de conmutación

Para poder ofrecer características de control remoto de llamadas a los usuarios, es necesario instalar al menos una puerta de enlace SIP/CSTA que se pueda conectar tanto a Lync Server como a la central de conmutación (PBX) existente del entorno. Una puerta de enlace SIP/CSTA es una puerta de enlace entre SIP y la CSTA (aplicación de telecomunicaciones para equipo). Independientemente del número de puertas de enlace que se hayan instalado, todos los usuarios se pueden configurar con tan solo una puerta de enlace o PBX. En caso de que la PBX existente carezca de una interfaz de SIP/CSTA, asegúrese de que implementa una puerta de enlace SIP/CSTA que admita la PBX, así como los protocolos de señalización específicos del proveedor de la PBX en cuestión. Para más información detallada sobre estas funciones, acuda directamente al proveedor.

Cuando esté todo listo para implementar una puerta de enlace SIP/CSTA que se pueda integrar en Lync Server para el control remoto de llamadas, póngase en contacto de nuevo con el proveedor de la puerta de enlace o consulte la documentación proporcionada por este sobre la sintaxis necesaria para la puerta de enlace y recopile la siguiente información:

  - URI del servidor de línea de la puerta de enlace

  - URI de línea de los usuarios que se van a asignar a la puerta de enlace.

La configuración anterior es necesaria durante la configuración de usuario y se debe especificar tal y como la puerta de enlace espera encontrarla para enrutar y conectarse a la PBX sin problemas.

Encontrará una lista de proveedores en el sitio web del Programa de interoperabilidad abierto de Comunicaciones unificadas de Microsoft en [http://go.microsoft.com/fwlink/?linkid=203309\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=203309%26clcid=0xc0a).

## Paso 2: Configurar Lync Server para enrutar solicitudes CSTA a la puerta de enlace SIP/CSTA

Es necesario crear rutas estáticas en los grupos de servidores de Lync Server hacia la dirección de destino (URI del servidor) de todas las puertas de enlace SIP/CSTA de la implementación en la que quiera enrutar solicitudes de control remoto de llamadas. Asimismo, es necesario crear una entrada de aplicación de confianza que se corresponda con cada dirección de destino. Cuando una puerta de enlace se designa como aplicación de confianza, recibe el estado de confianza para poder ejecutarse como parte del entorno de Lync Server, aun cuando se haya desarrollado por otro fabricante (y ejecuta lo que se conoce como *servicio externo* , ya que se trata de un servicio que no está integrado en el producto). Por último, si Lync Server va a conectarse a una puerta de enlace SIP/CSTA por medio de una conexión TCP (Protocolo de control de transmisión) en lugar de una conexión TLS (Seguridad de la capa de transporte), también es necesario definir la dirección IP de la puerta de enlace con Generador de topologías.

Para más información detallada sobre cómo configurar rutas estáticas, consulte [Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Para más información detallada sobre cómo configurar entradas de aplicación de confianza, consulte [Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Para más información detallada sobre cómo definir una dirección IP de puerta de enlace SIP/CSTA en Generador de topologías, consulte [Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

## Paso 3: Configurar usuarios de Lync para el control remoto de llamadas

Una vez que los usuarios se han habilitado para Lync Server, puede usar el Panel de control de Lync Server o el Shell de administración de Lync Server para habilitarlos para el control remoto de llamadas. Durante este paso es cuando se asigna a cada usuario un URI de servidor de línea y un URI de línea. El primero es el URI de SIP de la puerta de enlace SIP/CSTA que tiene previsto asignar al usuario, mientras que el segundo es el número de teléfono único asignado al usuario.

Para más información detallada sobre cómo configurar usuarios para el control remoto de llamadas, consulte [Habilitar a los usuarios de Lync para el control remoto de llamadas en Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

## Paso 4: Definir las reglas de normalización de números de teléfono de Lync Server

En los escenarios de control remoto de llamadas, Lync Server recurre a reglas de normalización de números de teléfono para convertir los números de teléfono procedentes de la puerta de enlace SIP/CSTA en formato E.164, ya que los números deben tener este formato estandarizado para que algunas funciones del control remoto de llamadas funciones correctamente. El control remoto de llamadas emplea las mismas reglas de normalización de números de teléfono que se definen para la normalización de los números de teléfono del Servicio de libreta de direcciones, que son distintas de las que se usan en Enterprise Voice.

Para más información detallada sobre el modo en que el control remoto de llamadas hace uso de las reglas de normalización de números de teléfono, consulte [Control remoto de llamadas y normalización de números de teléfono en Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Para más información detallada sobre las reglas de normalización de números de teléfono del Servicio de libreta de direcciones, consulte el tema [Administrar el servicio de libreta de direcciones en Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) en la documentación de introducción.

