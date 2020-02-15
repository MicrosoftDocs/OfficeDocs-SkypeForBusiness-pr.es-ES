---
title: 'Lync Server 2013: programación de detalles de reuniones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6537309f8c2a787c94897fa9f529c1abf8fd4791
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Detalles de programación de reuniones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Tras comprobar para asegurarse de que no hay ninguna otra reunión programada a la hora solicitada, el personal de soporte técnico de gran reunión que administra la solicitud programa la reunión en el grupo de servidores de reuniones grandes. Use el complemento de conferencia en línea para Lync que se instala con el cliente de Lync Server 2013 para realizar esta tarea, con las credenciales de un usuario habilitado para Lync Server en el grupo de reuniones de gran tamaño dedicado.

Para garantizar la mejor experiencia de usuario, es importante programar la reunión grande con los niveles de acceso adecuados y los valores de reunión que sean adecuados para las necesidades del organizador de la reunión. Se recomiendan las siguientes opciones de programación configuradas en las opciones de reunión de Lync:

  - Use un nuevo espacio de reunión para cada reunión grande en lugar de volver a usar el espacio de reunión dedicado.

  - Especifique el nivel de acceso de reunión de la siguiente manera:
    
      - Si al menos un invitado es externo a la organización, establezca el tipo de acceso de reunión en **Cualquiera (sin restricciones)**. Esto le habilita para evitar tener que administrar una sala de espera potencialmente grande cuando la reunión está en curso.
    
      - Si la reunión es solo interna, establezca el tipo de acceso de reunión en **Cualquiera de mi organización**.
        
        <div>
        

        > [!NOTE]  
        > Evite establecer el tipo de acceso de reunión en <STRONG>Personas de mi compañía a quien invito</STRONG> porque cuando usa esta configuración, los organizadores deben agregar todas las direcciones de correo electrónico de usuario a la lista de invitados y no puede invitar a un grupo de distribución.<BR>Evite establecer el tipo de acceso de reunión en <STRONG>Solo yo, el organizador de la reunión</STRONG> porque esta configuración requiere que todos los participantes de las reuniones, incluidos los moderadores, deben colocarse en la sala de espera en el tiempo de ejecución de la reunión. La persona responsable de la ejecución de la reunión grande debe supervisar entonces constantemente la lista de la sala de espera y admitir a nuevos usuarios que estén en la sala de espera.

        
        </div>

  - Permita a los usuarios que marquen desde teléfonos que entren en la reunión automáticamente activando la configuración para que los **autores de llamada entren directamente**.

  - Invitar de manera explícita a los siguientes usuarios:
    
      - Delegado y organizador de reunión (solicitante)
    
      - La lista de moderadores proporcionada por un solicitante de reunión
    
    <div>
    

    > [!NOTE]  
    > Si el tipo de acceso de reunión se establece en <STRONG>Las personas que yo elija</STRONG>, tiene que agregar de manera explícita a cada participante de una reunión grande como invitado de la reunión.

    
    </div>

  - Administrar de manera explícita moderadores, en lugar de establecer la opción de moderador a uno de los valores de promoción automática. Asegúrese de agregar los siguientes usuarios como moderadores:
    
      - Delegado y organizador de reunión (solicitante)
    
      - La lista de moderadores proporcionada por solicitantes de grandes reuniones
    
    <div>
    

    > [!NOTE]  
    > Al administrar de manera explícita moderadores, puede controlar el número de moderadores, de manera que pueda limitar moderadores a una presentación lo suficientemente pequeña como para hacer posible tener una reunión grande efectiva. Si la mayoría de los participantes de la reunión tienen el rol de asistente, ayuda a reducir la oportunidad de que las personas tomen de manera accidental el control de la presentación, la eliminación de una presentación de PowerPoint, poner/quitar el silencio de los moderadores, y otras interrupciones de la reunión.

    
    </div>

  - Active la configuración de **silenciar a todos los asistentes** para asegurarse de que solo los moderadores pueden difundir audio a la reunión.

  - Active la configuración para **bloquear el vídeo de los asistentes** para asegurarse de que solo los moderadores pueden difundir vídeo a la reunión.

En la siguiente figura se muestra la configuración recomendada para el complemento de conferencia en línea para Lync.

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

