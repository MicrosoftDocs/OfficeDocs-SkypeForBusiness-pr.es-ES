---
title: Conectar una aplicación de sucursal con funciones de supervivencia
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cada dispositivo de sucursal con funciones de supervivencia (SBA) está asociado con un grupo de servidores Front-End que actúa como un registrador de reserva para la SBA. Cuando el Front-End de grupo de servidores se migra a Skype para Business Server 2019, la SBA debe estar asociado al grupo de servidores Front-End mientras se actualiza el grupo de servidores, una vez que el grupo de servidores se ha migrado a Skype para Business Server 2019, la SBA puede asociarse volver a la actualizada E front- grupo de servidores de ND. Esto implica la eliminación de la SBA de la topología heredada en el generador de topología y, a continuación, agregar la SBA a la Skype para topología empresarial Server 2019. Los usuarios alojados en el heredado que SBA en primer lugar debe moverse a otro grupo de servidores Front-End antes de quitar la SBA de la topología. Una vez que se agrega la SBA a la Skype para Business Server 2019 topología, los usuarios pueden, a continuación, volver a moverse a la SBA. A continuación se resumen estos pasos:'
ms.openlocfilehash: ff35032d9abc5c1435e44dea7aca83d841b404c6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373752"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar una aplicación de sucursal con funciones de supervivencia

Cada dispositivo de sucursal con funciones de supervivencia (SBA) está asociado con un grupo de servidores Front-End que actúa como un registrador de copia de seguridad para la SBA. Cuando el grupo de servidores Front-End se migra a Skype para Business Server 2019, la SBA debe estar asociada desde el grupo de servidores Front-End mientras se actualiza el grupo de servidores. Después de que el grupo de servidores se ha migrado a Skype para Business Server 2019, se puede volver a asociar con el grupo de servidores Front-End actualizado la SBA. Esto implica la eliminación de la SBA de la topología heredada en el generador de topología y, a continuación, agregar la SBA a la Skype para topología empresarial Server 2019. Los usuarios alojados en el heredado que SBA en primer lugar debe moverse a otro grupo de servidores Front-End antes de quitar la SBA de la topología. Después de agrega la SBA a la Skype para Business Server 2019 topología, los usuarios pueden volver a moverse a la SBA. A continuación se resumen estos pasos:
  
1. Mover los usuarios de sucursal hospedados en la SBA heredada a otro grupo de servidores Front-End.
    
2. Quitar la SBA de la topología heredada para desconectar el grupo de servidores Front-End existente como un registrador de copia de seguridad.
    
3. Agregar la SBA a la Skype para Business Server 2019 topología y configuración de este nuevo grupo de servidores Front-End como registrador de reserva. 
    
4. Mover los usuarios de sucursal a la nueva Skype para Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Agregar el sitio de sucursal SBA heredado a la topología

1. Abra **el generador de topología**.
    
2. En el panel izquierdo, haga clic en **sitios de sucursal**y, a continuación, haga clic en **Nuevo sitio de sucursal**.
    
3. En el cuadro de diálogo **Definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba el nombre de la sucursal.
    
4. (Opcional) Haga clic en **Descripción**y, a continuación, escriba una descripción significativa para el sitio de sucursal.
    
5. Haga clic en **Siguiente**.
    
6. (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal** , realice una de las siguientes opciones: 
    
    1. Haga clic en **Ciudad**y, a continuación, escriba el nombre de la ciudad donde se encuentra el sitio de sucursal.
    
    2. Haga clic en **provincia o región**y, a continuación, escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
    3. Haga clic en **El código de país**y, a continuación, escriba el código de llamada de dos dígitos para el país o región en el que se encuentra el sitio de sucursal.
    
7. Haga clic en **siguiente**y, a continuación, si se usa una aplicación de sucursal con funciones de supervivencia o servidor en este sitio, asegúrese de desactive la casilla de verificación **Abrir el Asistente nuevo con funciones de supervivencia cuando se cierre este asistente** . Haga clic en **Finalizar**.
    
8. Para asociar la SBA heredada a la Skype para el grupo de servidores Front-End de Business Server 2019:
    
    1. Expanda el sitio de sucursal que se ha creado. 
    
    2. Haga clic en la versión heredada y, a continuación, haga clic en **nuevo**.
    
    3. Haga clic en **aplicación de sucursal con funciones de supervivencia**.
    
9. Siga las instrucciones en el Asistente para la que se abre. Para obtener información acerca de los elementos del asistente, vea    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Una aplicación de sucursal con funciones de supervivencia sólo puede asociarse con un almacén de supervisión. 
  
10. Si no se usa un servidor o una aplicación de sucursal con funciones de supervivencia en este sitio, desactive la casilla de verificación **Abrir el Asistente nuevo con funciones de supervivencia cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.
    
11. Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.
    

