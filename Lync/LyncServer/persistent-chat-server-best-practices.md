---
title: Procedimientos recomendados para el servidor de chat persistente
TOCTitle: Procedimientos recomendados para el servidor de chat persistente
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48276904
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Procedimientos recomendados para el servidor de chat persistente

 

_**Última modificación del tema:** 2012-10-06_

Cuando cree sus categorías y salones de Chat persistente y diseñe el ámbito y la pertenencia, las sugerencias siguientes pueden ayudarlo en su planeación:

  - Si la compañía no necesita la imposición de zonas de protección de datos confidenciales y no está concediendo acceso a usuarios federados, no limite el ámbito en el árbol de categorías. Ponga a todos los usuarios en el ámbito de la categoría raíz y cree todos los salones de chat en dicha categoría. Después, utilice únicamente las listas de pertenencia para conceder o restringir el acceso a cada salón de chat.

  - En la mayoría de casos, deberá habilitar a los usuarios para crear nuevos salones de chat, para que se puedan iniciar debates sobre temas nuevos en cualquier momento. Para ello, haga que la lista **Creators** sea la misma que la lista de **AllowedMembers**. Ahora bien, si desea que un solo equipo de soporte técnico central o usuarios designados puedan crear salones, convierta la lista **Creators** en el subconjunto apropiado.

  - Proporcione a cada salón de chat un nombre completo y un resumen de temas que lo ubique totalmente dentro de la organización. Como los usuarios no verán el nombre de categoría cuando usen el salón de chat, no puede basarse en el nombre de categoría para ayudar a los usuarios a ver lo que está previsto debatirse en el salón de chat.

  - Probablemente quiera tener un flujo de trabajo de creación de salones personalizado si desea implementar determinadas convenciones de nomenclatura o validaciones. La configuración de Chat persistente permite personalizar **RoomManagementUrl** para que lo hospede. Por ejemplo, cuando los usuarios hagan clic en **Crear un salón** en su cliente de Lync, se redirigirán a la solución personalizada.

  - Cree varios complementos para que le sea más fácil mejorar la experiencia de los salones de chat incorporando datos de negocio a los salones de chat. Los administradores deben registrar los complementos que desean permitir en el sistema. Los creadores y los administradores de salones de chat pueden elegir en una lista de complementos permitidos aquellos complementos que sean más adecuados para sus respectivos salones.

## Vea también

#### Otros recursos

[Administrar categorías, salones de chat y complementos en Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)

