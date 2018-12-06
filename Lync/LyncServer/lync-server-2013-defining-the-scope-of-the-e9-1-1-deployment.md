---
title: 'Lync Server 2013: Definición del ámbito de la implementación de E9-1-1'
TOCTitle: Definición del ámbito de la implementación de E9-1-1
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48274785
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definición del ámbito de la implementación de E9-1-1 en Lync Server 2013

 

_**Última modificación del tema:** 2012-06-06_

Antes de configurar Microsoft Lync Server 2013 para E9-1-1, debe planificar la implementación de su E9-1-1. Algunas de las cuestiones que se deben tener en cuenta son:

  - **¿Cuáles son las obligaciones legales y la directiva de su organización con respecto a E9-1-1?**  
    Los requisitos legales de E9-1-1 para sistemas PBX (llamados sistemas telefónicos de varias líneas o MLTS, en la jerga de E9-1-1) difieren de un estado a otro. Debe consultar a su equipo legal para comprender las obligaciones que podrían aplicarse a la implementación de Lync Server en sus ubicaciones geográficas pertinentes.

<!-- end list -->

  - **¿Qué áreas de la empresa deben habilitarse para E9-1-1?**  
    Puede habilitar E9-1-1 para las ubicaciones seleccionadas o para toda la empresa. Por ejemplo, puede tener distintos requisitos de E9-1-1 para oficinas en diferentes estados o quizás desee excluir sitios fuera de Estados Unidos.

<!-- end list -->

  - **¿Cómo implementará E9-1-1 en las sucursales?**  
    La resistencia de voz de las sucursales es un concepto que es importante tener en cuenta al implementar E9-1-1 en una sucursal. Si tiene troncos SIP de E-9-1-1 centralizados y se produce una interrupción en la red WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación de un Servicio de información de ubicaciones o conectarse al proveedor de servicios de emergencia. Lync Server proporciona varias estrategias para administrar la resistencia de voz en sucursales que incluyen las siguientes: disponer de redes de datos resistentes, implementar un tronco SIP en cada sucursal o redirigir llamas de emergencia a la puerta de enlace local durante interrupciones. Para obtener más información, consulte [Planificar la resistencia de voz en sitios de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**  
    La adquisición de ubicación automática está disponible solamente para los clientes situados dentro de la red de la organización, por lo que su organización debe decidir si admitir llamadas de E9-1-1 realizadas desde clientes de Lync que están fuera de la organización. Por ejemplo, ¿permitirá a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio del cliente? Si un cliente se encuentra fuera de la red empresarial, el cliente puede configurarse para solicitar al usuario una ubicación. Sin embargo, dado que estas ubicaciones proporcionadas por el usuario no pueden validarse previamente con la Guía de calles maestra (MSAG), el distribuidor del proveedor de servicios de emergencia deberá confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de enrutar la llamada al Punto de respuesta de seguridad pública (PSAP).
    

    > [!NOTE]
    > Los clientes de Lync de los usuarios que se conectan a la red de la organización mediante el uso de VPN pueden recoger información de dirección IP interna, pero debido a que estas direcciones no pueden usarse para identificar la ubicación del usuario real, es esencial que las subredes VPN se excluyan del Servicio de información de ubicaciones.



<!-- end list -->

  - **¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios de fuera de Estados Unidos?**  
    Puede que quiera proporcionar el enrutamiento de emergencia en áreas de la compañía donde no sirve el proveedor de servicios de emergencia (por ejemplo, en ubicaciones internacionales). Para ello, cree un sitio nuevo y, a continuación, asigne directivas de voz a los sitios que hagan referencia a un uso de RTC que enruta la llamada a través de la puerta de enlace local de RTC.

