---
title: Preparar un servidor único de Standard Edition (introducción)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Para comenzar la instalación de un servidor de Skype empresarial Server 2015 Standard Edition que contenga el almacén de administración central y otros servicios colocados, debe iniciar sesión como miembro del grupo de administradores locales en el servidor que va a conviértase en el servidor Standard Edition. En la página de preparación de un solo servidor Standard Edition se detallan los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
ms.openlocfilehash: cb8e370adc13d30d320aceb70218115991592257
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283622"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar un servidor único de Standard Edition (introducción)
 
Para comenzar la instalación de un servidor de Skype empresarial Server 2015 Standard Edition que contenga el almacén de administración central y otros servicios colocados, debe iniciar sesión como miembro del grupo de administradores locales en el servidor que va a conviértase en el servidor Standard Edition. En la página de **preparación de un solo servidor Standard Edition** se detallan los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
  
El objetivo de esta tarea específica es configurar un servidor Standard Edition como primer servidor de la infraestructura. Esta tarea instala el almacén de administración central, que es SQL Server Express, en el servidor Standard Edition. Si ya tiene implementado otro servidor Standard Edition u otro grupo de servidores front-end, debe hacer clic en **Cancelar**.
  
> [!NOTE]
> Después de completar esta tarea, instalará el generador de topología (si aún no lo ha instalado) y configurará el documento de topología. No podrá publicar el documento de topología hasta que tenga un almacén de administración central disponible, que se implementa completando la tarea descrita en este tema. 
  

