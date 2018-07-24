---
title: Solicitud de certificado (entidad de certificación)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Al solicitar un certificado a una entidad de certificación en línea (o CA; suelen ser servidores ubicados en la red interna) en la página Elija una entidad de certificación, aparecen dos opciones:'
ms.openlocfilehash: 860faad4bcbb78010cabf835817ad852aca1e66b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975403"
---
# <a name="certificate-request-certificate-authority"></a>Solicitud de certificado (entidad de certificación)
 
Al solicitar un certificado a una entidad de certificación en línea (o CA; suelen ser servidores ubicados en la red interna) en la página **Elija una entidad de certificación**, aparecen dos opciones:
  
1. Seleccionar una entidad de certificación de la lista detectada en el entorno.
    
2. Especificar otra entidad de certificación.
    
Si selecciona la primera opción, verá una lista desplegable que contiene todas las entidades de certificación basada en Windows Server que se detectaron en su entorno. Seleccione la entidad de certificación adecuada para el certificado. Quizá deba consultar al administrador de la entidad de certificación para saber qué entidad se debe elegir.
  
Si se inclina por la segunda opción, escriba el nombre de dominio completo y la instancia de entidad de certificación que usará para el certificado. Esta opción es la correcta si la entidad de certificación que quiere usar no se basa en servidores Windows; sin embargo, será válida para entidades basadas en servidores Windows.
  
> [!IMPORTANT]
> Asegúrese de confirmar las pertenencias a grupos que necesita para que la solicitud del certificado sea válida. Normalmente, las entidades de certificación tienen un requisito de permisos diferentes de los requisitos para instalar Skype para Business Server en servidores. Confirme con el administrador de la entidad de certificación los requisitos para solicitar el certificado. 
  

