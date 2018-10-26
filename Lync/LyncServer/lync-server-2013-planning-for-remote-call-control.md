---
title: 'Lync Server 2013: Planificar el control remoto de llamadas'
TOCTitle: Planificar el control remoto de llamadas
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48275559
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planificar el control remoto de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-05_

En Lync Server 2013, la compatibilidad con escenarios de control remoto de llamadas permite a los usuarios controlar sus teléfonos de central de conmutación (PBX) usando Lync 2013 en sus equipos de escritorio. En esta sección se describen las características del control remoto de llamadas y los requisitos necesarios para implementar el control remoto de llamadas.

Gracias a la integración entre una PBX y Lync Server 2013, los usuarios con control remoto de llamadas habilitado pueden usar la interfaz de usuario (UI) de Lync 2013 para controlar las llamadas de sus teléfonos PBX mediante las siguientes acciones:


> [!NOTE]
> Las funcionalidades de la PBX que hospeda el teléfono PBX de un usuario son las que determinan en última instancia las características de control remoto de llamadas disponibles para el usuario.



  - Efectuar una llamada realizada

  - Responder a una llamada entrante

  - Responder a una llamada entrante con un mensaje instantáneo
    

    > [!NOTE]
    > Es decir, cuando el número de teléfono del autor de la llamada puede asociarse a una dirección de mensajería instantánea de la lista de direcciones global (GAL) de la organización, de la lista de contactos de Lync del destinatario o de la organización de un socio federado.



  - Transferir una llamada

  - Desviar una llamada entrante

  - Poner llamadas en espera

  - Alternar entre varias llamadas simultáneas

  - Responder a una segunda llamada mientras se está participando en una llamada (es decir, poner llamadas en espera)

  - Marcar dígitos de tono de marcado de frecuencia múltiple (DTMF)

  - En la ventana Conversación, escribir notas en el programa Microsoft Office OneNote

Además, cuando un usuario tiene el control remoto de llamadas habilitado, Lync 2013 le proporciona la siguiente información de llamada:

  - Identificación de un autor de llamada mediante su nombre, si el número de teléfono del autor de la llamada figura en la lista de contactos del cliente de mensajería y colaboración de Microsoft Office Outlook, en la lista de contactos de Lync o en la GAL de la organización de un usuario con el control remoto de llamadas habilitado.

  - Últimas llamadas entrantes y realizadas, que se guardan en la carpeta Historial de conversaciones de Outlook.

  - Notificaciones de llamadas perdidas, que se envían a la carpeta Bandeja de entrada de Outlook del usuario, pero que se emiten únicamente si Lync se está ejecutando cuando se recibe la llamada entrante.

## Control remoto de llamadas y Telefonía IP empresarial

Como las características del control remoto de llamadas son independientes de las características de Telefonía IP empresarial y los usuarios no pueden estar habilitados para ambas opciones, Telefonía IP empresarial proporciona un subconjunto de características que está disponible también para los usuarios con el control remoto de llamadas habilitado. Si Telefonía IP empresarial está implementado, los usuarios con el control remoto de llamadas habilitado podrán usar Lync para acceder a las siguientes características de Telefonía IP empresarial:

  - Efectuar y recibir llamadas de audio de otro cliente de Lync

  - Unirse a la parte de audio de una conferencia creada por un usuario habilitado para Telefonía IP empresarial

## En esta sección

  - [Implementación de tareas para el control remoto de llamadas en Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

