---
title: Conectar una aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cada dispositivo de sucursal con supervivencia (SBA) está asociado con un grupo de servidores front-end que sirve como registrador de copias de seguridad de la SBA. Cuando el grupo de servidores front-end se migra a Skype empresarial Server 2019, SBA debe estar desvinculado del grupo front-end mientras se actualiza el grupo, una vez que el grupo se ha migrado a Skype empresarial Server 2019, la SBA se puede volver a asociar con la actualización frontal E Grupo ND. Esto implica eliminar la SBA de la topología heredada en el generador de topología y, a continuación, agregar el SBA a la topología de Skype empresarial Server 2019. Los usuarios alojados en el SBA heredado deben moverse primero a otro grupo de servidores front end antes de quitar SBA de la topología. Una vez agregada SBA a la topología de Skype empresarial Server 2019, esos usuarios podrán volver a la SBA. Estos pasos se resumen a continuación:'
ms.openlocfilehash: daeb061936ece02767e3299d2358d8e16ba09218
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813738"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar una aplicación de sucursal con funciones de supervivencia

Cada dispositivo de sucursal con supervivencia (SBA) está asociado con un grupo de servidores front-end que sirve como registrador de copias de seguridad de la SBA. Cuando el grupo de servidores front-end se migra a Skype empresarial Server 2019, SBA debe estar desvinculado del grupo de servidores front-end mientras se actualiza el grupo. Una vez que el grupo se ha migrado a Skype empresarial Server 2019, SBA se puede volver a asociar al grupo de servidores front-end actualizado. Esto implica eliminar la SBA de la topología heredada en el generador de topología y, a continuación, agregar el SBA a la topología de Skype empresarial Server 2019. Los usuarios alojados en el SBA heredado deben moverse primero a otro grupo de servidores front end antes de quitar SBA de la topología. Después de agregar SBA a la topología de Skype empresarial Server 2019, esos usuarios se pueden mover de nuevo a SBA. Estos pasos se resumen a continuación:
  
1. Mueva los usuarios alojados en el SBA heredado a otro grupo de servidores front-end.
    
2. Quite SBA de la topología heredada para desconectar el grupo de servidores front-end existente como registrador de la copia de seguridad.
    
3. Agregue SBA a la topología de Skype empresarial Server 2019 y configúrela como registrador de la copia de seguridad. 
    
4. Mueva a los usuarios de la sucursal al nuevo servidor de Skype empresarial 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Agregar el sitio de la sucursal de SBA heredado a su topología

1. Abra el **generador de topologías**.
    
2. En el panel de la izquierda, haga clic con el botón secundario en **sitios de sucursales**y luego haga clic en **nuevo sitio de sucursal**.
    
3. En el cuadro de diálogo **definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba el nombre del sitio de la sucursal.
    
4. Faculta Haga clic en **Descripción**y, a continuación, escriba una descripción para el sitio de la sucursal.
    
5. Haga clic en **Siguiente**.
    
6. Faculta En el cuadro de diálogo **definir siguiente sitio de sucursal** , realice una de las siguientes acciones: 
    
    1. Haga clic en **ciudad**y, a continuación, escriba el nombre de la ciudad en la que se encuentra el sitio de la sucursal.
    
    2. Haga clic en **Estado o región**y, a continuación, escriba el nombre del estado o la región en la que se encuentra el sitio de la sucursal.
    
    3. Haga clic en **prefijo internacional**y escriba el código de la llamada de dos dígitos para el país o la región en la que se encuentra el sitio de la sucursal.
    
7. Haga clic en **siguiente**y, después, si está usando un dispositivo o servidor de sucursal con la mayor supervivencia en este sitio, asegúrese de desactivar la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** . Haga clic en **Finalizar**.
    
8. Para asociar SBA heredado al grupo front-end de Skype empresarial Server 2019:
    
    1. Expanda el sitio de la sucursal que ha creado. 
    
    2. Haga clic con el botón derecho en versión heredada y luego haga clic en **nuevo**.
    
    3. Haga clic en **equipo de rama superviviente**.
    
9. Siga las instrucciones del asistente que se abre. Para obtener información sobre los elementos del asistente, consulte    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Un equipo de sucursal con la supervivencia solo puede asociarse con una tienda de supervisión. 
  
10. Si no usa un equipo o servidor de sucursal con la supervivencia en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.
    
11. Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.
    

