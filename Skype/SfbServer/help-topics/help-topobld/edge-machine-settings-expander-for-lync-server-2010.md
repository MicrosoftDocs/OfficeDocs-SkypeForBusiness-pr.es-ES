---
title: Expansor de configuración de equipo perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de los equipos de servidor perimetral como un único servidor perimetral o como equipos miembros de un grupo de servidores perimetrales, debe configurar las opciones de configuración de nombre de servidor y dirección IP:'
ms.openlocfilehash: 81fb33a2217431cd908156dab95e36cca0675f23
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604949"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de configuración de equipo perimetral para Lync Server 2010
 
Para editar las propiedades de los equipos de servidor perimetral como un único servidor perimetral o como equipos miembros de un grupo de servidores perimetrales, debe configurar las opciones de configuración de nombre de servidor y dirección **IP:**
  
- **Nombre interno o FQDN**: escriba el nombre del equipo tal como aparece en el sistema de nombres de dominio (DNS). 
    
- **Dirección IPv4 interna**: escriba la dirección IPv4 de la tarjeta de interfaz de red interna (NIC) de este equipo.
    
- Configurar la dirección **IPv4** **externa del servicio perimetral** de acceso asociada a este equipo
    
    > [!IMPORTANT]
    > Si ha seleccionado usar una sola dirección IP para la configuración del servidor perimetral, solo podrá editar la dirección IPv4 externa para el servicio perimetral de acceso. Los demás servicios perimetrales compartirán la misma dirección IPv4 que el servicio perimetral de acceso. 
  
- Si está disponible para editar, configure la dirección **IPv4** externa del servicio de conferencia **web** asociada a este equipo
    
- Si está disponible para editar, configure la dirección **IPv4** externa del servicio perimetral **A/V** asociada a este equipo
    
- Si está disponible para edición, configure la **Dirección IPv4 habilitada para NAT** asociada con este equipo.
    
    > [!IMPORTANT]
    > La propiedad de configuración de la dirección **IPv4** pública habilitada para NAT solo estará disponible para editar si optó por proporcionar traducción de direcciones de red (NAT) para el servicio perimetral A/V
  
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  

