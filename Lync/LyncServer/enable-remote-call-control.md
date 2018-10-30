---
title: Habilitar control de llamadas remoto
TOCTitle: Habilitar control de llamadas remoto
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48274396
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar control de llamadas remoto

 

_**Última modificación del tema:** 2012-10-02_

El control remoto de llamadas hace posible que los usuarios puedan controlar sus teléfonos de central de conmutación (PBX) de escritorio mediante Lync Server 2013. Si implementó el control remoto de llamadas en el entorno heredado y desea migrarlo a Lync Server 2013, debe realizar las siguientes tareas:

1.  Instale una puerta de enlace SIP/CSTA y configúrela para que se comunique con su PBX. Debe hacer este paso al implementar su grupo piloto de Lync Server 2013.

2.  Una vez que combina su topología y migra sus directivas y su configuración, configure Lync Server 2013 para enrutar las solicitudes CSTA a la puerta de enlace SIP/CSTA. Se trata de un paso manual que sigue a la migración automatizada. Para configurar el enrutamiento de solicitudes CSTA, lleve a cabo una de las siguientes acciones:
    
      - Quite las entradas de host autorizado heredadas (denominadas *entradas de servidor de confianza* en Lync Server 2013). Si va a migrar usuarios de la implementación heredada, asegúrese de que quita todas las entradas de host autorizado heredadas que creó para la puerta de enlace SIP/CSTA antes de configurar nuevas entradas de aplicación de confianza en el grupo piloto de Lync Server 2013. Para obtener información sobre cómo quitar las entradas de host autorizado heredadas, consulte [Quitar una entrada de host autorizada](remove-an-authorized-host-entry.md).
    
      - Configure una ruta estática para el control remoto de llamadas. Puede configurar una ruta estática para los grupos individuales en los que quiera usar el control remoto de llamadas, o bien configurar una ruta estática global para que la usen los grupos que no tengan una ruta grupal configurada expresamente. Para obtener información sobre cómo configurar la ruta estática, consulte [Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) en la documentación sobre implementación.
    
      - Configure una entrada de aplicación de confianza de control remoto de llamadas en cada grupo en el que quiera admitir el control remoto de llamadas. Para obtener información sobre cómo configurar una entrada de aplicación de confianza, consulte [Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) en la documentación sobre implementación.

3.  Si ha implementado una puerta de enlace SIP/CSTA que use el Protocolo de control de transmisión (TCP) para conectarse a Lync Server 2013, defina la dirección IP de la puerta de enlace en Topology Builder. Para obtener información sobre la definición de la dirección IP, consulte [Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) en la documentación sobre implementación.

4.  Configure usuarios de Lync 2013 para el control remoto de llamadas; para ello, habilite el control remoto de llamadas y asigne un identificador uniforme de recursos (URI) de servidor de línea y un URI de línea. Cuando migre los usuarios de la implementación heredada a Lync Server 2013, la configuración del control remoto de llamadas se migrará junto con el resto de configuraciones de los usuarios.

5.  Si personalizó las reglas de normalización de números de teléfono de la libreta de direcciones en la implementación heredada, cuando finalice la migración automatizada de las directivas y las configuraciones deberá realizar algunas tareas manuales para migrar estas reglas de normalización personalizadas. Si no personalizó ninguna regla, la libreta de direcciones se migra con el resto de la topología. Para obtener información detallada sobre cómo migrar manualmente las reglas de normalización personalizadas, consulte [Migrar la libreta de direcciones](migrate-address-book_1.md).

