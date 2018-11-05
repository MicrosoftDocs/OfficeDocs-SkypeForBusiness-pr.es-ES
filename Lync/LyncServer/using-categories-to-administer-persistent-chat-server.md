---
title: "Util. des catégories pour administrer le serveur de conversation permanente"
TOCTitle: "Util. des catégories pour administrer le serveur de conversation permanente"
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48276939
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar categorías para administrar el servidor de chat persistente

 

_**Última modificación del tema:** 2013-10-01_

La implementación del Servidor de chat persistente puede hospedar muchos salones de Chat persistente simultáneos. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de la categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y facilita la delegación y simplificación de la administración.


> [!NOTE]
> Aunque muchas de las características de administración de los salones de chat están disponibles en los equipos que ejecutan el Chat persistente (cliente de Lync) para el usuario, los administradores del Chat persistente (en el rol <STRONG>cspersistentchatadministrator</STRONG>) usan los cmdlets del Panel de control de Lync Server o del Windows PowerShell para crear o administrar categorías.



Los administradores del Chat persistente usan los cmdlets del Panel de control de Lync Server o del Windows PowerShell para crear y administrar categorías, y para diseñar el acceso a los salones de chat para los usuarios de su organización.

Los administradores de salones de Chat persistente, que tienen la capacidad de administrar uno o varios salones de chat, usan el cliente de Lync para iniciar una aplicación web de administración de salones para crear y administrar salones (o los clientes pueden crear soluciones y flujos de trabajo personalizados para invocarlos).Los administradores de Chat persistente pueden también usar los cmdlets del Panel de control de Lync Server o del Windows PowerShell para crear y administrar salones.


> [!NOTE]
> Un salón de Chat persistente no puede tener el mismo nombre que una categoría de Chat persistente.



Los administradores de los salones de chat pueden realizar cambios en todas las propiedades del salón de chat, salvo para cambiar la categoría del salón. No se les puede impedir ejecutar las acciones siguientes:

  - Deshabilitar un salón de chat

  - Cambiar el nombre de un salón de chat

  - Cambiar la descripción de un salón de chat

  - Cambiar el tipo de salón de chat (Auditorio o Normal)

  - Cambiar la privacidad de un salón (abierto o cerrado o secreto)

  - Agregar o quitar miembros

  - Agregar o quitar administradores de salones de chat

  - Agregar o quitar un complemento

  - Cambiar configuraciones como invitaciones (de acuerdo con lo permitido por la categoría)

## Administración jerárquica

Crear y administrar salones de Chat persistente es más fácil si se usan las categorías correctas. Un administrador de Chat persistente puede definir **AllowedMembers** y **Creators** para cada categoría, y también puede definir la configuración del salón de chat habitual, así como los comportamientos que se aplicarán a todos los salones de chat creados en la categoría. Los administradores de Chat persistente crean y administran categorías con los cmdlets del Panel de control de Lync Server o del Windows PowerShell.

Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Después de crear la categoría, pueden elegir usuarios, UO y grupos de usuarios en la lista **AllowedMembers** de la categoría, como administradores y miembros del salón de chat para administrar y participar en el salón.

Los salones de chat que se crean en una categoría cumplen las directivas y la configuración aplicada por la categoría (como quién puede pertenecer al salón, quién puede administrar el salón, si se permiten las cargas de archivos, si se envían invitaciones, etc).

