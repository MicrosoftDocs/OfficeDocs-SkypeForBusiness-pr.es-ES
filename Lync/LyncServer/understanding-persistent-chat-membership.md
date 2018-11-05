---
title: Introducción a la pertenencia al chat persistente
TOCTitle: Introducción a la pertenencia al chat persistente
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48276008
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Introducción a la pertenencia al chat persistente

 

_**Última modificación del tema:** 2013-02-22_

El acceso de usuarios a los salones Chat persistente se administra mediante la pertenencia; los usuarios deben ser miembros de un salón de chat para poder publicar y leer mensajes. Solo los **moderadores** que tengan una afiliación designada a los salones de chat pueden **publicar en salones de Auditorio**. Un Auditorio es un tipo de salón de chat (el otro es **Normal**), en el que solo los moderadores pueden publicar y todos pueden leer.

Además, los salones de Chat persistente funcionan según las reglas de una categoría. Para obtener más información sobre las categorías, consulte [Administrar categorías, salones de chat y complementos en Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), así como las secciones "Funcionamiento del ámbito de categoría" y "Estrategias de categorías de salón" más adelante en este tema.

Un administrador de Chat persistente puede crear y administrar categorías de salón de chat. Como parte de la creación y administración de categorías de salón de chat, el administrador de Chat persistente puede configurar entidades (grupos, contenedores y usuarios de Servicios de dominio de Active Directory) que tienen acceso para ser miembros o creadores de salones de chat de una categoría particular.

## Servicios de dominio de Active Directory y Chat persistente

El Servidor de chat persistente se basa en Active Directory para el grupo de servidores de usuarios de Chat persistente internos. Después de instalar el Chat persistente (cliente), puede agregar dominios de usuarios y grupos de usuarios a la categoría de salón. Puede agregar estos usuarios y grupos a la pertenencia de las categorías de salón.

> [!IMPORTANT]  
> Debe asegurarse de que no haya nombres duplicados para los usuarios que quieren realizar cambios en sus salones de Chat persistente. Si hubiera nombres de usuario duplicados, cámbielos por nombres diferentes para permitir a dichos usuarios realizar cambios. Si un usuario tiene nombres duplicados en Active Directory e intenta realizar cambios en sus salones, se mostrará un mensaje de error pidiendo al usuario que se ponga en contacto con el administrador.



## Funcionamiento del ámbito de categoría

Una categoría especifica todos los usuarios y grupos que pueden ser miembros en una lista de pertenencia de un salón de Chat persistente en la categoría en cuestión, en función de su propiedad **AllowedMembers**. Por ejemplo, si establece el valor de **AllowedMembers** de la categoría en contoso.com, cualquier grupo o usuario de *Contoso* se puede agregar como miembro a los salones de chat de dicha categoría. Si establece el valor de **AllowedMembers** de una categoría en *Sales* , solo los grupos y usuarios de esta lista de distribución se pueden agregar como miembros a los salones de chat de esa categoría. De forma similar, la propiedad **Creators** permite controlar quién puede crear salones de chat en esa categoría. Una vez creado el salón de chat, todos los miembros del grupo **AllowedMembers** pueden designarse como **Administrator** para las operaciones de administración continuadas en los salones (por ejemplo, cambios y aprobaciones de pertenencia como miembro).

Definir **AllowedMembers** y **Creators** para una categoría tiene las siguientes ventajas:

  - Todos los salones de chat de esta categoría se rigen por las restricciones establecidas en el nivel de la categoría. Puede usarlo para segregar salones de chat en función de las necesidades empresariales y las directivas de acceso.

  - Un usuario de la lista **Creators** puede crear nuevos salones de chat en esa categoría. Si quiere implementar un sistema en el que un número restringido de personal de la organización pueda crear salones de chat, se puede usar este control para cumplir ese requisito.

## Estrategias de categoría de salón

La lista **AllowedMembers** de una categoría debe incluir todos los usuarios que usarán alguno de los salones de Chat persistente en esta categoría. En función de sus requisitos para proteger los datos empresariales y garantizar un nivel de acceso adecuado, quizás quiera definir una o varias categorías para especificar quién puede buscar salones y participar en ellos. Si quiere permitir que solo un conjunto determinado de usuarios (departamento de soporte técnico central o solo empleados a tiempo completo) pueda crear salones, puede definir el ámbito de la lista **Creators** de una categoría para satisfacer ese requisito.

Las categorías también se pueden usar para crear zonas de protección. Las zonas de protección evitan conflictos de intereses en una organización. Por ejemplo, un administrador puede crear salones de chat en una categoría solo para comerciales, mientras que los salones de chat de otra categoría son solo para analistas.


> [!NOTE]
> En Lync Server 2013, Servidor de chat persistente, no se admite el acceso a los usuarios federados. Si hay chats de usuarios federados en las versiones anteriores de Servidor de chat persistente, se migrarán. Los usuarios federados se agregan como entidades deshabilitadas.



## Restringir los miembros a grupos de usuarios

Cuando se agrega un dominio a una categoría, los grupos de usuarios cuyos objetos de grupo estén incluidos en dicho dominio estarán disponibles para que pueda especificarlos como miembros de los salones de esa categoría.

Como regla general, es recomendable usar contenedores de Active Directory, como dominios y unidades organizativas, para definir las listas **AllowedMembers** y **Creators**. Puede agregar objetos de cualquier dominio a una lista **AllowedMembers** o **Creators**. Solo los objetos de la lista **AllowedMembers** o **Creators** se pueden agregar a los salones de esa categoría.

