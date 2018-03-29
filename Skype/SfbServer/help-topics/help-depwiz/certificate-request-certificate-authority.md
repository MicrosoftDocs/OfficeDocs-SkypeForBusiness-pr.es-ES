---
title: Solicitud de certificado (entidad de certificación)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Al realizar una solicitud de certificado a una entidad emisora de certificados en línea (CA) (por lo general, estos son los servidores que se encuentran en la red interna) en la página Elija una entidad emisora de certificados (CA), se presentan con dos opciones:'
ms.openlocfilehash: 6fea8ba9500e1612ff13796f4c58550687baa99a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-certificate-authority"></a>Solicitud de certificado (entidad de certificación)
 
Al solicitar un certificado a una entidad de certificación en línea (o CA; suelen ser servidores ubicados en la red interna) en la página **Elija una entidad de certificación**, aparecen dos opciones:
  
1. Seleccionar una entidad de certificación de la lista detectada en el entorno.
    
2. Especificar otra entidad de certificación.
    
Si selecciona la primera opción, verá una lista desplegable que contiene todas las autoridades de certificación basada en Windows Server que se detecten en su entorno. Seleccione la entidad de certificación adecuada para el certificado. Quizá deba consultar al administrador de la entidad de certificación para saber qué entidad se debe elegir.
  
Si se inclina por la segunda opción, escriba el nombre de dominio completo y la instancia de entidad de certificación que usará para el certificado. Esta opción es la correcta si la entidad de certificación que quiere usar no se basa en servidores Windows; sin embargo, será válida para entidades basadas en servidores Windows.
  
> [!IMPORTANT]
> Asegúrese de confirmar las pertenencias a grupos que necesita para que la solicitud del certificado sea válida. Normalmente, las autoridades de certificación tienen un requisito de permisos diferentes de los requisitos para instalar Skype para Business Server en servidores. Confirme con el administrador de la entidad de certificación los requisitos para solicitar el certificado. 
  

