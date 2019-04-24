---
title: Expansor de configuración de equipo perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de los equipos de servidor perimetral como un único servidor perimetral o como equipos miembros de un grupo de servidores perimetrales, configurar opciones de configuración de dirección IP y de nombre de servidor:'
ms.openlocfilehash: f0125ba8d9c7ff181aff0a29f69a5077b1ad0818
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225366"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de configuración de equipo perimetral para Lync Server 2010
 
Para editar las propiedades de los equipos de servidor perimetral como un único servidor perimetral o como equipos miembros de un grupo de servidores perimetrales, configure la configuración de **nombre del servidor y la configuración de dirección IP** :
  
- **Nombre interno o FQDN**: escriba el nombre del equipo al que se hace referencia en el sistema de nombres de dominio (DNS). 
    
- **Dirección IPv4 interna**: escriba la dirección IPv4 de la tarjeta de interfaz de red interna (NIC) para este equipo.
    
- Configurar el **servicio de servidor perimetral de acceso** **dirección IPv4 externa** asociada con este equipo
    
    > [!IMPORTANT]
    > Si seleccionó para utilizar una sola dirección IP para la configuración del servidor perimetral, sólo podrá editar la dirección IPv4 externa para el servicio de servidor perimetral de acceso. Los otros servicios perimetrales comparten la misma dirección IPv4 como el servicio de servidor perimetral de acceso. 
  
- Si está disponible para edición, configure el **servicio de conferencia Web** **dirección IPv4 externa** asociada con este equipo
    
- Si está disponible para edición, configure la **A / servicio perimetral A/v** **dirección IPv4 externa** asociada con este equipo
    
- Si está disponible para edición, configure la **dirección IPv4 habilitada para NAT** asociada con este equipo.
    
    > [!IMPORTANT]
    > La propiedad de configuración de **dirección IPv4 habilitada para NAT** sólo estará disponible para edición si opta por proporcionar la traducción de direcciones de red (NAT) en lugar de A / servicio perimetral A/v
  
  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda** Abre esta pantalla de ayuda.
  

