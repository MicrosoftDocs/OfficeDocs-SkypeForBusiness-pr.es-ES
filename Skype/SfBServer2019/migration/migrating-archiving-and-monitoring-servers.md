---
title: Migrar los servidores de archivado y supervisión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Si implementó el servidor de archivado y el servidor de supervisión en el entorno heredado, puede implementar estos servidores en el entorno de Skype Empresarial Server 2019 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar archivado y supervisión al grupo piloto de Skype Empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: a5b839a1eb7d460a57d6adf36901c50479f203ad
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596174"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrar los servidores de archivado y supervisión

Si implementó el servidor de archivado y el servidor de supervisión en el entorno heredado, puede implementar estos servidores en el entorno de Skype Empresarial Server 2019 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar archivado y supervisión al grupo piloto de Skype Empresarial Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración. 
  
Si desea contar con la funcionalidad de archivado y de supervisión durante la el proceso de migración, tenga en cuenta lo siguiente:
  
- Los datos de archivado y los datos de supervisión no se mueven a la Skype Empresarial Server de 2019. Los datos de los que se hace una copia de seguridad antes de retirar el entorno heredado serán su historial de actividad en el entorno heredado.
    
- La versión heredada del servidor de archivado y el servidor de supervisión solo se puede asociar a un grupo de servidores front-end heredado. En Skype Empresarial Server 2019, el archivado y la supervisión ya no son roles de servidor, sino servicios integrados en el grupo de servidores front-end Skype Empresarial Server 2019.
    
- Durante el tiempo en que coexisten las implementaciones heredadas y Skype Empresarial Server 2019, la versión heredada del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios que se han almacenado en grupos heredados. El archivado y la supervisión en Skype Empresarial Server 2019 recopilan datos para los usuarios que se Skype Empresarial Server grupos de servidores de 2019.
    
    > [!NOTE]
    > Durante la fase de migración cuando todavía está usando el servidor perimetral heredado con el nuevo grupo piloto de Skype Empresarial Server 2019, la versión heredada del servidor de archivado sigue recopilando datos para los usuarios que se encuentran en grupos heredados y el archivado en Skype Empresarial Server 2019 recopila datos para usuarios que se encuentran en grupos de servidores de Skype Empresarial Server 2019. 
  
- Si usa una solución de archivado y supervisión de terceros junto con archivado y supervisión en Skype Empresarial Server 2019, consulte con su proveedor sobre cuándo y cómo debe integrar la solución de terceros con Skype Empresarial Server 2019.
    

