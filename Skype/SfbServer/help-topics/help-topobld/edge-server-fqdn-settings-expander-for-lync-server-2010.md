---
title: Configuración de borde servidor FQDN Expander para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades de configuración externo, configure lo siguiente:'
ms.openlocfilehash: 2954c9add818e67f471cfb97893fef42e862bea3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Configuración de borde servidor FQDN Expander para Lync Server 2010
 
Para definir las propiedades de **configuración externo**, configure lo siguiente:
  
Seleccione el **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** casilla de verificación si desea definir diferentes IP y FQDN del grupo de direcciones para audio y vídeo y conferencias por Internet.
  
> [!NOTE]
> Si decide no seleccionar la casilla de verificación separe las direcciones IP y FQDN, debe proporcionar puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral. El único nombre de dominio completo que va a configurar es el FQDN asociado con el servicio de servidor perimetral de acceso. 
  
Seleccione el **A / servicio V perimetral es NAT habilitado** casilla de verificación si desea que el servicio borde V a utilizar una red la dirección de dirección IP de traducción (NAT) y la configuración.
  
Para los servicios habilitados de borde, escribe un **Pool FQDN** y un puerto en la ficha **puertos**
  
- Definir un puerto que identifica de forma única el servicio y el FQDN del grupo de servidores de **servicio de servidor perimetral de acceso** .
    
- Definir el FQDN del grupo de **servicio perimetral de conferencia Web** (si permiten separar el FQDN y la dirección IP para conferencias por Internet y A / V no está seleccionada) y un puerto que identifica el servicio.
    
- Definir la **A / servicio perimetral V** Pool FQDN (si permiten separar el FQDN y la dirección IP para conferencias por Internet y A / V no está seleccionada) y un puerto que identifica el servicio.
    
 **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
 **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
 **Ayuda** Abre esta pantalla de ayuda.
  

