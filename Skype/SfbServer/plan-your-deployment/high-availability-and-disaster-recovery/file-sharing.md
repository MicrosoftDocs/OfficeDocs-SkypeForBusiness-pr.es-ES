---
title: Alta disponibilidad de uso compartido de archivos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Obtenga información sobre cómo garantizar la alta disponibilidad de los recursos compartidos de archivos en Skype Empresarial Server, mediante DFS.
ms.openlocfilehash: 4d443425f453d63694511d13c6d3a84893058daa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802900"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Alta disponibilidad de uso compartido de archivos en Skype Empresarial Server
 
Obtenga información sobre cómo garantizar la alta disponibilidad de los recursos compartidos de archivos en Skype Empresarial Server, mediante DFS.
  
Para garantizar la alta disponibilidad para el uso compartido de archivos en su implementación de Skype Empresarial Server, puede usar el Sistema de archivos distribuido (DFS). DFS admite la conmutación por error de un servidor de archivos a otro del mismo centro de datos. Para una implementación a gran escala, recomendamos que use servidores de archivos dedicados que se emparejen mediante DFS. Para obtener más información sobre DFS en Windows Server 2012, vea [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) . Para obtener información sobre DFS en Windows Server 2008, vea [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) .
  
En función del tamaño de la red y de la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos de un sitio o usar un par por grupo de servidores front-end.
  
DFS es un mecanismo de replicación de archivos de tipo “mejor esfuerzo” (best effort), sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado. Una conmutación por error entre servidores DFS debe completarse rápidamente, pero el retraso en la replicación de datos puede impedir que los usuarios puedan continuar trabajando en curso cuando se produce la conmutación por error.
  
Si usa DFS y el almacén de datos del archivo compartido es fundamental, debe hacer una copia de seguridad de los recursos compartidos de archivos con frecuencia, como cada 4 a 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.
  

