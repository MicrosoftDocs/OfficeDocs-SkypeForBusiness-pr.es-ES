---
title: "Características y funciones de los servidores front-end, la MI y la presencia"
TOCTitle: Características y funcionalidades de los servidores front-end, la mensajería instantánea y la presencia
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48274305
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Características y funcionalidades de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-17_

Los servidores front-end ofrecen la mayor parte de la funcionalidad de Lync Server. Hay dos ediciones disponibles: Lync Server Enterprise Edition, que está diseñada principalmente para organizaciones grandes y Lync Server Standard Edition, que está diseñada principalmente para organizaciones más pequeñas que desean una inversión de hardware más pequeña y no requieren alta disponibilidad. Ambas ediciones admiten todas las cargas de trabajo de Lync Server, incluidas la mensajería instantánea, la presencia, la conferencia y Enterprise Voice.

La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.

> [!IMPORTANT]  
> Cuando los clientes de Lync y Communicator participan en una comunicación de uno a uno, este proceso se suele denominar “punto a punto”. Técnicamente, los dos clientes se comunican en una conversación de uno a uno, con la unidad de control multipunto de mensajería instantánea (IMMCU) en medio. La IMMCU es un componente de Servidor front-end. Si se sitúa la IMMCU en el flujo de trabajo de comunicación necesario, se permite el registro de detalles de las llamadas y otras características que habilita el Servidor front-end. La comunicación se lleva a cabo desde un puerto de origen dinámico del cliente al puerto TLS/TCP/5061 del Servidor front-end (suponiendo que se use la seguridad de la capa de transporte recomendada). Por motivos de diseño, la comunicación de punto a punto (así como la MI de varios participantes) solo es posible cuando Lync Server y la IMMCU están activos y disponibles.



*Presencia* proporciona información a los usuarios acerca del estado de los otros usuarios en la red. El estado de presencia de un usuario proporciona información que ayuda a los demás usuarios a decidir si deben intentar ponerse en contacto con él y si deben usar la mensajería instantánea, el teléfono o el correo electrónico. El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible. Este estado de presencia se visualiza como un icono de presencia en Lync y otras aplicaciones con detección de presencia, incluido el cliente de colaboración y la mensajería de Microsoft Outlook, las tecnologías de Microsoft SharePoint, los servicios o el servidor de portal o los servicios de equipo de Microsoft Word y el software de hojas de cálculo de Microsoft Excel. El icono del estado de presencia representa la disponibilidad y la disposición de comunicación del usuario.

