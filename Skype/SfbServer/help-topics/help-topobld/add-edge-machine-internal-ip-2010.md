---
title: Agregar borde IP interna de equipo 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.
ms.openlocfilehash: 2fedde361e252d400f4362add4757df3f0c40057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-machine-internal-ip-2010"></a>Agregar borde IP interna de equipo 2010
 
Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.
  
- En la **dirección IPv4 interno**, escriba la dirección IP del servidor de borde que desea agregar al grupo.
    
- En **Nombre completo interno**, escriba el nombre de dominio completo (FQDN) del servidor de borde que desea agregar al grupo.
    
El FQDN que especifique debe ser idéntico al nombre del equipo que está configurado en el servidor. Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo del sistema de nombres de dominio (DNS) en el nombre del equipo para implementarse como un servidor perimetral que no está unido a un dominio. Para obtener más información acerca de cómo agregar un sufijo DNS para un nombre de equipo, vea [Configurar DNS para el soporte de borde](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)
  

