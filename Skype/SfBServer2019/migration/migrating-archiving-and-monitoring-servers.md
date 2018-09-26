---
title: Migración de servidores de archivado y supervisión
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si ha implementado el servidor de archivado y el servidor de supervisión en el entorno heredado, puede implementar estos servidores en su Skype para entorno empresarial Server 2019 después de migrar los grupos de servidores Front-End. Sin embargo, si la funcionalidad de supervisión y archivado son críticos para la organización, debe agregar el archivado y supervisión a su Skype para el grupo piloto Business Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.
ms.openlocfilehash: cd6e3bf7ef04ca7906b707a30211d0c22d22d837
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028757"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migración de servidores de archivado y supervisión

Si ha implementado el servidor de archivado y el servidor de supervisión en el entorno heredado, puede implementar estos servidores en su Skype para entorno empresarial Server 2019 después de migrar los grupos de servidores Front-End. Sin embargo, si la funcionalidad de supervisión y archivado son críticos para la organización, debe agregar el archivado y supervisión a su Skype para el grupo piloto Business Server 2019 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración. 
  
Si desea la funcionalidad de archivado y supervisión durante el proceso de migración, tenga en cuenta las siguientes consideraciones:
  
- Datos de archivado y supervisión de datos no se mueven a la Skype para la implementación empresarial Server 2019. Los datos que la copia de seguridad antes de retirar el entorno heredado será el historial de actividad en el entorno heredado.
    
- La versión heredada de servidor de archivado y el servidor de supervisión se puede asociar solo con un grupo de servidores Front-End heredado. En Skype para Business Server 2019, archivado y supervisión ya no son roles de servidor, pero los servicios integrados en el Skype para el grupo de servidores Front-End de Business Server 2019.
    
- Durante el tiempo que su heredado y Skype para las implementaciones empresariales Server 2019 coexistir, la versión antigua de servidor de archivado y el servidor de supervisión recopilar datos para los usuarios alojados en grupos de servidores heredados. Archivado y supervisión de Skype para Business Server 2019 recopilan datos para los usuarios alojados en Skype para grupos de negocio Server 2019.
    
    > [!NOTE]
    > Durante la fase de migración cuando se siguen usando su servidor perimetral heredado con el nuevo Skype para Business Server 2019 continúa con el grupo piloto, la versión antigua de servidor de archivado para recopilar datos para los usuarios alojado en grupos de servidores heredados y Archiving en Skype para la empresa Servidor 2019 recopila datos de los usuarios alojados en Skype para grupos de negocio Server 2019. 
  
- Si usa un tercero de archivado y supervisión solución junto con archivado y supervisión de Skype para 2019 de servidor empresarial, póngase en contacto con su proveedor acerca de cómo y cuándo es necesario integrar la solución de terceros con Skype para Business Server 2019.
    

