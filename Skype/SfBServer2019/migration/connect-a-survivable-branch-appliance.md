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
description: 'Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copias de seguridad para SBA. Cuando el grupo de servidores front-end se migra a Skype empresarial Server 2019, la SBA debe estar desasociada del grupo de servidores front-end mientras se actualiza el grupo, una vez que el grupo se ha migrado a Skype empresarial Server 2019, la SBA puede volver a asociarse con el grupo de servidores front-end actualizado. Esto implica eliminar la SBA de la topología heredada en el generador de topologías y, a continuación, agregar la SBA a la topología de Skype empresarial Server 2019. Los usuarios hospedados en la SBA heredada deben moverse primero a otro grupo de servidores front-end antes de quitar SBA de la topología. Una vez agregada SBA a la topología de Skype empresarial Server 2019, estos usuarios se pueden volver a mover a SBA. Estos pasos se sintetizan a continuación:'
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751552"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar una aplicación de sucursal con funciones de supervivencia

Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copias de seguridad para SBA. Cuando el grupo de servidores front-end se migra a Skype empresarial Server 2019, la SBA debe estar desasociada del grupo de servidores front-end mientras se actualiza el grupo. Una vez que el grupo se ha migrado a Skype empresarial Server 2019, la SBA se puede volver a asociar con el grupo de servidores front-end actualizado. Esto implica eliminar la SBA de la topología heredada en el generador de topologías y, a continuación, agregar la SBA a la topología de Skype empresarial Server 2019. Los usuarios hospedados en la SBA heredada deben moverse primero a otro grupo de servidores front-end antes de quitar SBA de la topología. Una vez agregada SBA a la topología de Skype empresarial Server 2019, estos usuarios se pueden volver a mover a SBA. Estos pasos se sintetizan a continuación:
  
1. Mueva los usuarios de sucursal hospedados en SBA heredado a otro grupo de servidores front-end.
    
2. Quite SBA de la topología heredada para desconectar el grupo de servidores front-end existente como registrador de reserva.
    
3. Agregue SBA a la topología de Skype empresarial Server 2019 y configure este nuevo grupo de servidores front-end como registrador de reserva. 
    
4. Mueva los usuarios de sucursal al nuevo SBA de Skype empresarial Server 2019.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Agregar sitio de sucursal de SBA heredado a la topología

1. Abra el **Generador de topologías**.
    
2. En el panel izquierdo, haga clic con el botón secundario en **sitios de sucursal**y haga clic en **nuevo sitio de sucursal**.
    
3. En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre ** y escriba el nombre del sitio de sucursal.
    
4. (Opcional) Haga clic en **Descripción ** y escriba una descripción significativa para el sitio de sucursal.
    
5. Haga clic en **Siguiente**.
    
6. (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones: 
    
    1. Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.
    
    2. Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
    3. Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.
    
7. Haga clic en **siguiente**y, si está usando una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, asegúrese de desactivar la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** . Haga clic en **Finalizar**.
    
8. Para asociar la SBA heredada al grupo de servidores front-end de Skype empresarial Server 2019:
    
    1. Expanda el sitio de sucursal que ha creado. 
    
    2. Haga clic con el botón secundario en versión heredada y, a continuación, haga clic en **nuevo**.
    
    3. Haga clic en **aplicación de sucursal**con funciones de supervivencia.
    
9. Siga las indicaciones del asistente que se abrirá. Para obtener información acerca de los elementos del asistente, consulte    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Una aplicación de sucursal con funciones de supervivencia solo se puede asociar con un almacén de supervisión. 
  
10. Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.
    
11. Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.
    

