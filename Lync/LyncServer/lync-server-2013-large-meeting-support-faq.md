---
title: "Preguntas frecuentes sobre la compatibilidad de reuniones grandes en Lync Server 2013"
TOCTitle: "FAQ sur la prise en charge des grandes réunions Lync Server 2013"
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48274895
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preguntas frecuentes sobre la compatibilidad de reuniones grandes en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-22_

Las siguientes secciones ofrecen respuestas a preguntas habituales para crear y ejecutar reuniones grandes.

## P: ¿Cuántos usuarios pueden participar en una reunión grande?

El modelo de usuario de Lync Server especifica límites de 250 usuarios en un grupo de servidores compartidos o 1000 usuarios en un grupo de usuarios dedicado a reuniones grandes, pero estos números solo representan el número de usuarios que hemos probado y solo para el conjunto específico de hardware que hemos usado en nuestra prueba. En función de nuestra prueba, se recomiendan dichos límites para tamaños máximos. Sin embargo, se controla el número real de participantes permitidos en reuniones de su organización configurando una o varias directivas de conferencia (que configura mediante cmdlets de Windows PowerShell en el Shell de administración de Lync Server o mediante el Panel de control de Lync Server). El número que especifica en una directiva de conferencia puede ser cualquier número entero de 32 bits comprendido entre 1 y 4.294.967.295, pero el tamaño recomendado se encuentra entre 2 y 250 participantes, inclusive; y el valor predeterminado es 250.

## P: ¿Cuántas reuniones u otras cargas de trabajo puedo tener en un grupo de servidores que está dedicado a reuniones grandes?

Para garantizar la mejor experiencia de usuario en reuniones grandes de hasta 1000 participantes, se recomienda hospedar únicamente una única reunión grande cada vez en un grupo de servidores dedicado a reuniones grandes. También se recomienda no permitir que se ejecute cualquier otra carga de trabajo en dicho grupo de servidores cuando la reunión grande se encuentre en curso.

## P: ¿Deberían los organizadores de reuniones grandes hospedarse en el grupo de servidores dedicado?

No. Se recomienda no hospedar ningún usuario distinto del personal dedicado que administra la programación de reuniones grandes en el grupo de servidores dedicado. Esto evita que tráfico de comunicaciones en tiempo real provoque problemas con reuniones grandes que se hospedan en el grupo de servidores. Debería programar reuniones grandes en el grupo de servidores dedicado con una cuenta de usuario del personal de programación de reuniones grandes. Debería agregar la cuenta de usuario del organizador de reuniones (el usuario que solicita una reunión grande) como moderador para las reuniones grandes.

## P: ¿Qué modalidades de medios puedo usar en una reunión grande?

Las reuniones grandes con un máximo de 1000 usuarios pueden incluir audio, video, uso compartido de PowerPoint, pizarras y sondeo de presencia.

## P: ¿Puedo usar la mensajería instantánea de grupo (MI) en reuniones grandes?

Sí. Sin embargo, los números grandes de mensajes instantáneos, especialmente cuando se envían por un gran número de participantes de reunión, pueden afectar a la experiencia del usuario debido a problemas con el desplazamiento de texto rápido en la ventana de MI. La entrega de una gran cantidad de mensajes instantáneos de un máximo de 1000 usuarios también puede introducir cargas de servidor importantes, que pueden afectar al rendimiento. Por lo general, la MI solo es necesaria para preguntas y respuestas.

## ¿Pueden los usuarios unirse a reuniones grandes marcando desde un teléfono?

Sí. Si el grupo de usuarios de Lync Server 2013 está correctamente implementado y habilitado para conferencia de marcado, los usuarios podrán unirse a las reuniones grandes marcando. Nuestra prueba ha mostrado que hasta un máximo de un 15% de los 1000 usuarios pueden unirse a la reunión grande por un período de 10 minutos.

## P: ¿Puedo hospedar reuniones grandes en una topología virtual?

No hemos probado reuniones grandes en una topología virtual, por lo que no admitimos el uso de máquinas virtuales para hospedar un grupo de servidores dedicados para reuniones grandes.

