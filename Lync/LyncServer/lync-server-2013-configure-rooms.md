---
title: 'Lync Server 2013: Configurar salones'
TOCTitle: Configurar salones
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48275940
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar salones en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

La configuración de salones de Chat persistente suelen gestionarla los usuarios u otros equipos centrales mediante Interfaz de la línea de comandos Windows PowerShell; normalmente, los administradores no administran los salones de chat. Sin embargo, si tiene que crear y administrar salones de chat, puede usar Interfaz de la línea de comandos Windows PowerShell o agregarse como miembro a un salón y usar el cliente Lync 2013.

Para más información sobre cómo configurar salones de chat con la Interfaz de la línea de comandos Windows PowerShell, vea "Administrar salones" en [Configuración del servidor de chat persistente con cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

## Administración de datos en salones de chat

Servidor de chat persistente permite a los usuarios colaborar enviando mensajes a salones de Chat persistente. Los datos persisten en el servidor, y los miembros del salón pueden obtener acceso a los datos, incluido el historial. No obstante, los usuarios con diferentes roles pueden tener un acceso diferente a los datos de persistencia, como se describe en la lista siguiente.

  - Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado. También pueden quitar o reemplazar mensajes que se consideren inapropiados para un salón de chat específico.

  - Los usuarios finales, incluidos los autores de mensajes, no pueden eliminar contenido de ningún salón de chat.

  - Los administradores de los salones de chat pueden deshabilitar salones, pero no pueden eliminarlos. Solo los administradores pueden eliminar un salón de chat una vez creado.

Si se elimina un mensaje, no se puede deshacer la acción. Sin embargo, los mensajes eliminados pueden restaurarse si hay una copia de seguridad. Si está habilitado un Servidor de cumplimiento de Chat persistente, los mensajes antiguos persisten en la base de datos de cumplimiento.


> [!NOTE]
> Este uso de datos del salón de chat se aplica a la Lync Server 2013, aplicación API de Servidor de chat persistente, salvo si está implicado un rol de administrador. El API Servidor de chat persistente no se puede usar para realizar ninguna operación del administrador. Debe realizar estas operaciones en Shell de administración de Lync Server.


