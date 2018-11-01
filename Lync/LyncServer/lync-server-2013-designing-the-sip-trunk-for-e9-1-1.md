---
title: 'Lync Server 2013: Diseño de troncos SIP para E9-1-1'
TOCTitle: Diseño de troncos SIP para E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48275252
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Diseño de troncos SIP para E9-1-1 en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server usa troncos SIP para conectar una llamada de emergencia con el proveedor de servicios E9-1-1. Puede configurar un tronco SIP de servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal. Sin embargo, si el vínculo WAN entre el sitio del autor de la llamada y el sitio que aloja el tronco SIP del servicio de emergencia no está disponible, una llamada realizada por un usuario en el sitio desconectado necesitará un registro de uso de teléfono especial en la directiva de voz de usuario que enrute la llamada al ECRC a través de la puerta de enlace de la red telefónica conmutada pública (RTC) local. Lo mismo sucede si se aplica un control de admisión de llamadas a la llamada.


> [!NOTE]
> Hay dos formas de implementar un tronco SIP en un entorno de Lync Server: 
> <UL>
> <LI>
> <P>Use Servidores de mediación de host múltiple que usan sus interfaces enrutadas públicamente y orientadas hacia fuera para comunicarse con el proveedor de troncos SIP.</P>
> <LI>
> <P>Use un controlador de borde de sesión (SBC) local para proporcionar un punto de demarcación segura entre los Servidores de mediación y los servicios del proveedor de troncos SIP.</P></LI></UL>Si elige el último método, asegúrese de que el modelo y la marca SBC que elija admite el paso de datos de ubicación PIDF-LO (Presence Information Data Format Location Object, en inglés) como parte de su SIP INVITE. De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación. Para más información sobre los SBC certificados, vea "Infraestructura apta para Microsoft Lync" en <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>.<BR>Los proveedores de servicios E9-1-1 suministran acceso a un par de SBC para redundancia. Necesita tomar varias decisiones respecto a la topología de Servidor de mediación y con la configuración del enrutamiento de llamadas. ¿Tratará ambos SBC como pares iguales y usará el enrutamiento round robin para las llamadas entre ellos? ¿O designará un SBC como principal y el otro como secundario?



Para obtener detalles sobre cómo implementar un tronco SIP en Lync Server, vea [¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md). Las siguientes preguntas le ayudarán a decidir cómo implementar troncos SIP para E9-1-1.

  - **¿Tendrá que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**  
    Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que reemplazarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerde que si va a conectar con proveedores de servicios de emergencia en Internet público y debe garantizar la confidencialidad de las llamas de emergencia, es necesario el cifrado IPSec.

<!-- end list -->

  - **¿Está diseñada su implementación de E9-1-1 para tolerar desastres?**  
    Como se trata de una solución de emergencia, la resistencia es importante. Implemente los Servidores de mediación principal y secundario y los troncos SIP en ubicaciones que toleren desastres. Es recomendable implementar el Servidor de mediación principal lo más cerca posible de los usuarios a los que admite y enrutar las llamadas de conmutación por error a través del Servidor de mediación secundario (ubicado en un área geográfica distinta).

<!-- end list -->

  - **¿Deberá implementar un tronco SIP independiente para cada sucursal?**  
    Lync Server proporciona varias estrategias para controlar la resistencia de voz en las sucursales: disponer de redes de datos resistentes, implementar un tronco SIP en cada sucursal o redirigir las llamadas a la puerta de enlace local durante las interrupciones. Para más información, vea [Enlace troncal SIP de sitios de sucursal en Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**  
    Lync Server no atiende las llamadas de emergencias de forma diferente a una llamada normal. Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) puede afectar de forma negativa a una configuración de E9-1-1. Las llamadas de emergencia se pueden bloquear o enrutar a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están enrutando las llamadas de emergencia. Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se deben enrutar manualmente al ECRC.

