---
title: Compatibilidad para grandes reuniones mediante Lync Server 2013
TOCTitle: Compatibilidad para grandes reuniones mediante Lync Server 2013
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48275216
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad para grandes reuniones mediante Lync Server 2013

 

_**Última modificación del tema:** 2012-10-03_

Las reuniones grandes no siguen el modelo de prueba descrito en la sección anterior porque tienen las siguientes características:

  - El formato de la reunión es una presentación de uno a varios.

  - Uno o unos pocos usuarios son presentadores y todo el mundo participa solo como asistentes.

  - El uso compartido de una presentación de PowerPoint es la actividad principal de colaboración de datos.

  - Se necesita audio y también se puede usar vídeo.

  - Una persona dedicada, generalmente el organizador de la reunión o un asistente del organizador, configura la reunión con suficiente antelación.

  - El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y el salón de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.

La compatibilidad con grandes reuniones de hasta 1.000 usuarios requiere abordar problemas relacionados con el modelo de hardware compartidos y el modelo sin reserva.

Para tener suficientes recursos de CPU y memoria para reuniones de hasta 1.000 usuarios, el Servidores front-end que hace de host no debe ser el host de ninguna carga de trabajo de mensajería instantánea (MI), presencia o de Telefonía IP empresarial. Tampoco debe alojar otras reuniones, independientemente de su tamaño. Esto significa que para alojar reuniones de hasta 1.000 usuarios es necesario configurar un grupo de Lync Server independiente dedicado a alojar grandes reuniones de hasta 1.000 usuarios.

Un grupo de Lync Server dedicado a grandes reuniones debe hospedar únicamente una reunión con un máximo de 1.000 usuarios al mismo tiempo, por lo que es necesario reservar horas de reunión con antelación a través de un proceso de programación extraordinaria para garantizar la compatibilidad dedicada del Servidores front-end. Para admitir más de una gran reunión al mismo tiempo, recomendamos configurar varios grupos de grandes reuniones dedicados.

Recomendamos que una persona dedicada ejecute y supervise la parte en línea de una gran reunión. Esta persona podría ser el organizador, el delegado del organizador o presentador, o un miembro del equipo de soporte técnico de la gran reunión, dependiendo de las preferencias de la organización.

En las secciones siguientes, se describe cómo implementar un grupo dedicado para grandes reuniones, incluidas las prácticas recomendadas para el uso de Lync Server 2013 para admitir escenarios de granes reuniones.

## En esta sección

  - [Configurar el soporte para grandes reuniones](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Administración de reuniones grandes](lync-server-2013-managing-large-meetings.md)

