---
title: Alta disponibilidad del uso compartido de archivos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Obtenga más información sobre cómo asegurar la alta disponibilidad de los recursos compartidos de archivos en Skype empresarial Server con DFS.
ms.openlocfilehash: c04c3acd009dd59a3894a62d08395db19c6d2368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815938"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Alta disponibilidad del uso compartido de archivos en Skype empresarial Server
 
Obtenga más información sobre cómo asegurar la alta disponibilidad de los recursos compartidos de archivos en Skype empresarial Server con DFS.
  
Para garantizar la alta disponibilidad del uso compartido de archivos en su implementación de Skype empresarial Server, puede usar el sistema de archivos distribuido (DFS). DFS admite la conmutación por error de un servidor de archivos a otro dentro del mismo centro de datos. Para una implementación de gran escala, te recomendamos usar servidores de archivos dedicados que se emparejan con DFS. Para obtener más información sobre DFS en Windows Server 2012, [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)consulte. Para obtener información sobre DFS en Windows Server 2008, [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)consulte.
  
Según el tamaño de la red y la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos en un sitio o usar un par por grupo de servidores front-end.
  
DFS es un mecanismo de replicación de archivos de mejor esfuerzo, sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado. La conmutación por error entre servidores DFS debe completarse rápidamente, pero el retraso de replicación de datos puede evitar que los usuarios puedan continuar trabajando en curso cuando se produzca la conmutación por error.
  
Si usa DFS y el almacén de datos en el recurso compartido de archivos es crítico, necesita realizar una copia de seguridad de los recursos compartidos de archivos con frecuencia, por ejemplo cada 4 u 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.
  

