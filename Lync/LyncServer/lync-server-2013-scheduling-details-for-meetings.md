---
title: Detalles de la programación
TOCTitle: Detalles de la programación
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48274958
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Detalles de la programación

 

_**Última modificación del tema:** 2012-10-04_

Tras comprobar para asegurarse de que no hay ninguna otra reunión programada a la hora solicitada, el personal de soporte técnico de gran reunión que administra la solicitud programa la reunión en el grupo de servidores de reuniones grandes. Use el Complemento para conferencia en línea para Lync que está instalado con el cliente de Lync Server 2013 para llevar a cabo esta tarea, usando las credenciales de un usuario habilitado para Lync Server en el grupo de servidores de reuniones grandes dedicado.

Para garantizar la mejor experiencia de usuario, es importante programar la reunión grande con los niveles de acceso adecuados y los valores de reunión que sean adecuados para las necesidades del organizador de la reunión. Se recomiendan los siguientes valores de programación configurados en Lync Opciones de reunión:

  - Use un nuevo espacio de reunión para cada reunión grande en lugar de volver a usar el espacio de reunión dedicado.

  - Especifique el nivel de acceso de reunión de la siguiente manera:
    
      - Si al menos un invitado es externo a la organización, establezca el tipo de acceso de reunión en **Cualquiera (sin restricciones)**. Esto le habilita para evitar tener que administrar una sala de espera potencialmente grande cuando la reunión está en curso.
    
      - Si la reunión es solo interna, establezca el tipo de acceso de reunión en **Cualquiera de mi organización**.
        

        > [!NOTE]
        > Evite establecer el tipo de acceso de reunión en <STRONG>Personas de mi compañía a quien invito</STRONG> porque cuando usa esta configuración, los organizadores deben agregar todas las direcciones de correo electrónico de usuario a la lista de invitados y no puede invitar a un grupo de distribución.<BR>Evite establecer el tipo de acceso de reunión en <STRONG>Solo yo, el organizador de la reunión</STRONG> porque esta configuración requiere que todos los participantes de las reuniones, incluidos los moderadores, deben colocarse en la sala de espera en el tiempo de ejecución de la reunión. La persona responsable de la ejecución de la reunión grande debe supervisar entonces constantemente la lista de la sala de espera y admitir a nuevos usuarios que estén en la sala de espera.



  - Permita a los usuarios que marquen desde teléfonos que entren en la reunión automáticamente activando la configuración para que los **autores de llamada entren directamente**.

  - Invitar de manera explícita a los siguientes usuarios:
    
      - Delegado y organizador de reunión (solicitante)
    
      - La lista de moderadores proporcionada por un solicitante de reunión
    

    > [!NOTE]
    > Si el tipo de acceso de reunión se establece en <STRONG>Las personas que yo elija</STRONG>, tiene que agregar de manera explícita a cada participante de una reunión grande como invitado de la reunión.



  - Administrar de manera explícita moderadores, en lugar de establecer la opción de moderador a uno de los valores de promoción automática. Asegúrese de agregar los siguientes usuarios como moderadores:
    
      - Delegado y organizador de reunión (solicitante)
    
      - La lista de moderadores proporcionada por solicitantes de grandes reuniones
    

    > [!NOTE]
    > Al administrar de manera explícita moderadores, puede controlar el número de moderadores, de manera que pueda limitar moderadores a una presentación lo suficientemente pequeña como para hacer posible tener una reunión grande efectiva. Si la mayoría de los participantes de la reunión tienen el rol de asistente, ayuda a reducir la oportunidad de que las personas tomen de manera accidental el control de la presentación, la eliminación de una presentación de PowerPoint, poner/quitar el silencio de los moderadores, y otras interrupciones de la reunión.



  - Active la configuración de **silenciar a todos los asistentes** para asegurarse de que solo los moderadores pueden difundir audio a la reunión.

  - Active la configuración para **bloquear el vídeo de los asistentes** para asegurarse de que solo los moderadores pueden difundir vídeo a la reunión.

La siguiente ilustración muestra la configuración recomendada para el Complemento para conferencia en línea para Lync.

![Opciones de reunión de conferencia](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "Opciones de reunión de conferencia")

