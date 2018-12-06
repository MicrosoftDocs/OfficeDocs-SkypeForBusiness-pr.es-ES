---
title: 'Lync Server 2013: Inclusión del departamento de seguridad'
TOCTitle: Inclusión del departamento de seguridad
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48275201
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Inclusión del departamento de seguridad en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-02_

Puede que su compañía requiera que el departamento de seguridad participe en una llamada de emergencia. Para ayudarle a decidir cómo integrar el departamento de seguridad en la implementación de E9-1-1, deberá responder a las preguntas que se indican a continuación.

  - **¿Desea que el departamento de seguridad reciba una notificación cuando haya una llamada de emergencia?**  
    Puede configurar la directiva de ubicación para que Lync Server envíe una alerta de mensajería instantánea (incluida la ubicación de la persona que llama) que conecte a la persona que realiza la llamada de emergencia con el personal de seguridad. Entonces el departamento de seguridad puede confirmar que hay una emergencia.

<!-- end list -->

  - **¿Desea que el departamento de seguridad establezca una conferencia en todas las llamadas de emergencia?**  
    En el caso de que el proveedor de servicios de emergencia lo permita, puede configurar la directiva de ubicación para incluir un número de devolución de llamada ante cada llamada de emergencia. Este número lo usa después el proveedor para que el personal de seguridad establezca una conferencia en cada llamada de emergencia.


> [!NOTE]
> En caso necesario, puede configurar personal de emergencia diferente para cada directiva de ubicación. Esto permite personalizar la respuesta para las diferentes áreas de su empresa o crear un comportamiento diferente para llamadas de emergencia originadas en el interior en contraposición con las realizadas en el exterior de la red. Puede usar grupos de distribución para especificar el personal al que desea notificar.


