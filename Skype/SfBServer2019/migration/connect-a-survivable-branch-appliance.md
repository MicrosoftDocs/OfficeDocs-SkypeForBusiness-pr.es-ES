---
title: Conectar una aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copia de seguridad para el SBA. Cuando el grupo de servidores front-end se migra a Skype Empresarial Server 2019, el SBA debe desasociarse del grupo de servidores front-end mientras se actualiza el grupo de servidores, Una vez que el grupo se ha migrado a Skype Empresarial Server 2019, el SBA se puede volver a asociar al grupo de servidores front-end actualizado. Esto implica eliminar el SBA de la topología heredada en el Generador de topologías y, a continuación, agregar el SBA a la topología de Skype Empresarial Server 2019. Los usuarios que se aloen en el SBA heredado primero deben moverse a otro grupo de servidores front-end antes de quitar el SBA de la topología. Una vez que el SBA se agrega a la topología de Skype Empresarial Server 2019, dichos usuarios pueden volver a la SBA. Estos pasos se sintetizan a continuación:'
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113346"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar una aplicación de sucursal con funciones de supervivencia

Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copia de seguridad para el SBA. Cuando el grupo de servidores front-end se migra a Skype Empresarial Server 2019, el SBA debe desasociarse del grupo de servidores front-end mientras se actualiza el grupo. Después de migrar el grupo a Skype Empresarial Server 2019, el SBA se puede volver a asociar al grupo de servidores front-end actualizado. Esto implica eliminar el SBA de la topología heredada en el Generador de topologías y, a continuación, agregar el SBA a la topología de Skype Empresarial Server 2019. Los usuarios que se aloen en el SBA heredado primero deben moverse a otro grupo de servidores front-end antes de quitar el SBA de la topología. Después de agregar el SBA a la topología de Skype Empresarial Server 2019, dichos usuarios pueden volver a la SBA. Estos pasos se sintetizan a continuación:
  
1. Mueva los usuarios de sucursal que se alomen en el SBA heredado a otro grupo de servidores front-end.
    
2. Quite SBA de la topología heredada para desconectar el grupo de servidores front-end existente como registrador de copia de seguridad.
    
3. Agregue SBA a la topología de Skype Empresarial Server 2019 y configure este nuevo grupo de servidores front-end como registrador de copia de seguridad. 
    
4. Mueva los usuarios de sucursal al nuevo SBA de Skype Empresarial Server 2019.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Agregar un sitio de sucursal SBA heredado a la topología

1. Abra el **Generador de topologías**.
    
2. En el panel izquierdo, haga clic con el botón secundario en **Sitios de sucursal** y, a continuación, haga clic en Nuevo sitio de **sucursal.**
    
3. En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre** y escriba el nombre del sitio de sucursal.
    
4. (Opcional) Haga clic en **Descripción** y escriba una descripción significativa para el sitio de sucursal.
    
5. Haga clic en **Siguiente**.
    
6. (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones: 
    
    1. Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.
    
    2. Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
    3. Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.
    
7. Haga **clic en** Siguiente y, a continuación, si usa una aplicación de sucursal con funciones de supervivencia o un servidor en este sitio, asegúrese de borrar la casilla Abrir el Nuevo Asistente para supervivencia **cuando** se cierre este asistente. Haga clic en **Finalizar**.
    
8. Para asociar el SBA heredado al grupo de servidores front-end de Skype Empresarial Server 2019:
    
    1. Expanda el sitio de sucursal que ha creado. 
    
    2. Haga clic con el botón secundario en versión heredada y, a continuación, haga clic en **Nuevo**.
    
    3. Haga **clic en Aplicación de sucursal con funciones de supervivencia.**
    
9. Siga las indicaciones del asistente que se abrirá. Para obtener información acerca de los elementos del asistente, vea    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Una aplicación de sucursal con funciones de supervivencia solo se puede asociar a un almacén de supervisión. 
  
10. Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.
    
11. Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.
