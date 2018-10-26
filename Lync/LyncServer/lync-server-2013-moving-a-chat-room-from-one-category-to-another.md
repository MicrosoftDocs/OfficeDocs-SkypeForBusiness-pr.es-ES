---
title: "Lync Server 2013 : Déplacement d’une salle de conv. d’une cat. vers une autre"
TOCTitle: Mover un salón de chat de una categoría a otra
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48275814
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover un salón de chat de una categoría a otra en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Recomendamos que no cambie la categoría de un salón Chat persistente después de crear el salón de chat. Sin embargo, si el administrador del salón de chat tiene privilegios de **Creador** en otra categoría, puede mover el salón de una categoría a otra. El salón no se eliminará y volverá a crearse. Es un cambio de asociación dentro de la base de datos.

Ocasionalmente podrá realizarse un cambio de categoría del salón de chat. Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se eliminan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría. Por ejemplo, si un usuario era miembro del salón y ya no es un **AllowedMember** en la nueva categoría, la pertenencia del salón se modificará y el usuario se eliminará de el.

Para obtener detalles acerca de cómo mover un salón de chat con el Interfaz de la línea de comandos Windows PowerShell vea "Administración de salones" en [Configuración del servidor de chat persistente con cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para más información sobre la configuración de salones de chat, vea [Configurar salones en Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación de implementación.

