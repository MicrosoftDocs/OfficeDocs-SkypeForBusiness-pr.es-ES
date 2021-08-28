---
title: Solicitud de certificado (entidad de certificación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Al realizar una solicitud de certificado a una entidad de certificación en línea (CA) (normalmente, se trata de servidores que están en la red interna) en la página Elegir una entidad de certificación (CA), se le presentan dos opciones:'
ms.openlocfilehash: 96f601a26f64802e93d776438dfc92b50f3ae76a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591834"
---
# <a name="certificate-request-certificate-authority"></a>Solicitud de certificado (entidad de certificación)
 
Al realizar una solicitud de certificado a una entidad de certificación en línea (CA) (normalmente, se trata de servidores que están en la red interna) en la página Elegir una entidad de certificación **(CA),** se le presentan dos opciones:
  
1. Seleccionar una entidad de certificación de la lista detectada en el entorno.
    
2. Especificar otra entidad de certificación.
    
Si selecciona la primera opción, verá una lista desplegable que contiene todas las Windows de certificación basadas en servidor que se detectan en el entorno. Seleccione la entidad de certificación adecuada para el certificado. Quizá deba consultar al administrador de la entidad de certificación para saber qué entidad se debe elegir.
  
Si selecciona la segunda opción, escriba el nombre de dominio completo (FQDN) y la instancia de ca para la entidad de certificación que usará para el certificado. Esta opción es adecuada si la CA que desea usar no es una CA basada en servidor de Windows, sino que funcionará para Windows CA basadas en servidor.
  
> [!IMPORTANT]
> Asegúrese de confirmar las pertenencias a grupos que necesita para realizar correctamente la solicitud de certificado. Normalmente, las entidades de certificación tienen un requisito de permiso diferente de los requisitos para instalar Skype Empresarial Server servidores. Confirme con el administrador de la entidad de certificación los requisitos para solicitar el certificado. 
  

