---
title: Archivo de uso compartido de alta disponibilidad en Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Obtenga información sobre cómo asegurar una alta disponibilidad de los recursos compartidos de archivos en Skype para Business Server, el uso de DFS.
ms.openlocfilehash: 645aa70ffc0c42cddb6941c9766cb91bed898dc8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989912"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Archivo de uso compartido de alta disponibilidad en Skype para Business Server
 
Obtenga información sobre cómo asegurar una alta disponibilidad de los recursos compartidos de archivos en Skype para Business Server, el uso de DFS.
  
Para asegurar una alta disponibilidad para compartir archivos en su Skype para la implementación de Business Server, puede usar el sistema de archivos distribuido (DFS). DFS admite la conmutación por error de un servidor de archivos a otro dentro del mismo centro de datos. Para una implementación de gran escala, te recomendamos usar servidores de archivos dedicados que se emparejan con DFS. Para obtener más información acerca de DFS en Windows Server 2012, consulte [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384). Para obtener información acerca de DFS en Windows Server 2008, consulte [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).
  
Dependiendo del tamaño de su red y la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos en un sitio o usar un par por grupo de servidores Front-End.
  
DFS es un mecanismo de replicación de archivos de mejor esfuerzo, sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado. Una conmutación por error entre servidores DFS debe realizarse rápidamente, pero el retraso de replicación de datos puede impedir que los usuarios puedan continuar el trabajo en curso cuando se produce la conmutación por error.
  
Si usa DFS y el almacén de datos en el recurso compartido de archivos es crítico, necesita realizar una copia de seguridad de los recursos compartidos de archivos con frecuencia, por ejemplo cada 4 u 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.
  

