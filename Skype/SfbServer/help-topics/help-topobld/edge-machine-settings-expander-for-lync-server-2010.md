---
title: Borde máquina configuración Expander para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de equipos servidor perimetral como un único servidor perimetral o equipos miembros de un grupo de borde, configurar el nombre del servidor y la configuración de dirección IP:'
ms.openlocfilehash: d1bc35683ff70e1666a46d478aa97b3bcc3d5593
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Borde máquina configuración Expander para Lync Server 2010
 
Para editar las propiedades de equipos servidor perimetral como un único servidor perimetral o equipos miembros de un grupo de borde, configurar **nombre del servidor** y la configuración de dirección IP:
  
- **Nombre interno o FQDN**: escriba el nombre del equipo al que se hace referencia en el sistema de nombres de dominio (DNS). 
    
- **Dirección IPv4 interno**: escriba la dirección IPv4 de la tarjeta de interfaz de red interna (NIC) para este equipo.
    
- Configurar el **servicio acceso perimetral de** **dirección IPv4 externos** asociados a este equipo
    
    > [!IMPORTANT]
    > Si ha seleccionado utilizar una única dirección IP para la configuración del servidor de borde, sólo podrá modificar la dirección IPv4 externa para el servicio de servidor perimetral de acceso. Los demás servicios de borde compartirán la misma dirección IPv4 como el servicio de servidor perimetral de acceso. 
  
- Si está disponible para editar, configurar el **servicio de conferencias Web** **dirección IPv4 externos** asociados a este equipo
    
- Si disponible para editar, configurar el **A / servicio perimetral V** **dirección IPv4 externos** asociados a este equipo
    
- Si está disponible para editar, configure la **dirección IPv4 pública habilitado para NAT** asociada con este equipo.
    
    > [!IMPORTANT]
    > Sólo estará disponible para modificar si opta por proporcionar la traducción de direcciones de red (NAT) en lugar de A la propiedad de configuración de **dirección IPv4 pública habilitado para NAT** / servicio perimetral V
  
 **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
 **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
 **Ayuda** Abre esta pantalla de ayuda.
  

