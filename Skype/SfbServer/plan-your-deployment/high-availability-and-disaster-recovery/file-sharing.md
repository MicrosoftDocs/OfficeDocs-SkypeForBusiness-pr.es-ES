---
title: Alta disponibilidad del uso compartido de archivos en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Obtenga información sobre cómo garantizar la alta disponibilidad de los recursos compartidos de archivos en Skype para Business Server, mediante DFS.
ms.openlocfilehash: f96e4aaca70c501425528b12207eeab01027c9a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="file-sharing-high-availability-in-skype-for-business-server-2015"></a>Alta disponibilidad del uso compartido de archivos en Skype Empresarial Server 2015
 
Obtenga información sobre cómo garantizar la alta disponibilidad de los recursos compartidos de archivos en Skype para Business Server, mediante DFS.
  
Para garantizar la alta disponibilidad para compartir archivos en tu Skype para la implementación de Business Server, puede utilizar el sistema de archivos distribuido (DFS). DFS admite la conmutación por error de un servidor de archivos a otro dentro del mismo centro de datos. Para una implementación de gran escala, te recomendamos usar servidores de archivos dedicados que se emparejan con DFS. Para obtener más información acerca de DFS en Windows Server 2012, consulte [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384). Para obtener información acerca de DFS en Windows Server 2008, consulte [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).
  
Dependiendo del tamaño de la red y la cantidad de resiliencia que desee, puede utilizar un par de servidores para alojar todos los recursos compartidos de archivos en un sitio o utilice un par por cada grupo de Front-End.
  
DFS es un mecanismo de replicación de archivos de mejor esfuerzo, sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado. Una conmutación por error entre servidores DFS debe realizarse rápidamente, pero el retraso de la replicación de datos puede evitar que los usuarios tengan la posibilidad de continuar el trabajo en curso cuando se produce la conmutación por error.
  
Si usa DFS y el almacén de datos en el recurso compartido de archivos es crítico, necesita realizar una copia de seguridad de los recursos compartidos de archivos con frecuencia, por ejemplo cada 4 u 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.
  

