---
title: Solicitud de certificado (entidad de certificación)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Al solicitar un certificado a una entidad de certificación en línea (o CA; suelen ser servidores ubicados en la red interna) en la página Elija una entidad de certificación, aparecen dos opciones:'
ms.openlocfilehash: 6c52a46bf40211d05ea47205d2573627910d3ba6
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796761"
---
# <a name="certificate-request-certificate-authority"></a>Solicitud de certificado (entidad de certificación)
 
Al solicitar un certificado a una entidad de certificación en línea (o CA; suelen ser servidores ubicados en la red interna) en la página **Elija una entidad de certificación**, aparecen dos opciones:
  
1. Seleccionar una entidad de certificación de la lista detectada en el entorno.
    
2. Especificar otra entidad de certificación.
    
Si selecciona la primera opción, verá una lista desplegable que contiene todas las entidades de certificación basadas en Windows Server que se detectan en su entorno. Seleccione la entidad de certificación adecuada para el certificado. Quizá deba consultar al administrador de la entidad de certificación para saber qué entidad se debe elegir.
  
Si se inclina por la segunda opción, escriba el nombre de dominio completo y la instancia de entidad de certificación que usará para el certificado. Esta opción es la correcta si la entidad de certificación que quiere usar no se basa en servidores Windows; sin embargo, será válida para entidades basadas en servidores Windows.
  
> [!IMPORTANT]
> Asegúrese de confirmar las pertenencias a grupos que necesita para que la solicitud del certificado sea válida. Normalmente, las entidades emisoras de certificados tienen un requisito de permiso diferente de los requisitos para instalar Skype empresarial Server en servidores. Confirme con el administrador de la entidad de certificación los requisitos para solicitar el certificado. 
  

