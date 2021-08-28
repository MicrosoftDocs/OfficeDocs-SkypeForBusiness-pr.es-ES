---
title: Editar expansor de configuración perimetral para Lync Server 2010
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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Para editar la configuración del servidor perimetral o el grupo de servidores perimetrales, configure las siguientes propiedades:'
ms.openlocfilehash: b7784e15d7446a51dfa9aed03dd1154bba157485
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635334"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar expansor de configuración perimetral para Lync Server 2010
 
Para editar la configuración del servidor perimetral o el grupo de servidores perimetrales, configure las siguientes propiedades: 
  
 **General**
  
- **FQDN** de grupo interno: el nombre de dominio completo del grupo interno es la identidad del servidor perimetral o grupo de servidores perimetrales, tal como se define en el registro de host del sistema de nombres de dominio (DNS) (A o AAAA para IPv6).
    
- Seleccione Habilitar la federación para este grupo de servidores perimetrales **(puerto 5061)** si desea habilitar el servidor perimetral o el grupo de servidores perimetrales para la federación con otros asociados del protocolo de inicio de sesión.
    
    > [!IMPORTANT]
    > Solo puede definir un servidor perimetral o un grupo perimetral de forma activa para la federación. La configuración mostrada en la captura de pantalla asociada indica que otro servidor perimetral o grupo de servidores perimetrales ya está configurado para la federación. El registro SRV de DNS externo para federación (_sipfederationtls._tcp. ) apuntará al servidor perimetral o al grupo de \<external domain name\> servidores perimetrales para la federación. 
  
- El puerto de replicación de configuración interna **(HTTPS),** de forma predeterminada en el puerto TCP 4443, es el puerto en el que se replica la copia local (es decir, local a los servidores perimetrales) del almacén de administración central. La copia local del almacén de administración central se encuentra en la base de datos **RTCLOCAL** SQL Server en cada equipo. La replicación es uni- nica, iniciada desde el servidor de administración central (o, el servidor front-end o grupo de servidores front-end que contiene el rol servidor de administración central) a los servidores perimetrales y es un puerto de interfaz interna.
    
  **Selección del próximo salto**
  
- Seleccione para la lista el **grupo de servidores de próximo salto**. Defina un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end para asumir este rol. El grupo de servidores del próximo salto es el servidor o grupo de servidores que aceptará mensajes SIP entrantes de la interfaz interna del servidor perimetral o del grupo perimetral y enviará SIP saliente a la interfaz interna perimetral.
    
    > [!NOTE]
    > El director es un rol opcional y si decide no implementar directores, los servidores front-end (un solo equipo o grupo de servidores) asumirán el rol director. 
  
  **Configuración externa**
  
Esta sección de las propiedades permite editar las propiedades de la configuración externa del servidor perimetral o grupo de servidores perimetrales. Pueden modificarse las siguientes propiedades:
  
- Active la casilla Habilitar fqdn y dirección IP independientes para conferencias web y **A/V** si desea asignar direcciones IP distintas y nombres de dominio completos a cada servicio de servidor perimetral.
    
    > [!NOTE]
    > Si decide no activar la casilla, debe usar puertos independientes para cada servicio perimetral. Cada servicio perimetral compartirá el FQDN definido para el servicio perimetral de acceso y, por lo tanto, usará la misma dirección IP. Cada servicio perimetral debe identificarse de forma única mediante una dirección IP distinta y el mismo puerto, o la misma dirección IP y valores de puerto únicos. 
  
- Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.
    
- Para editar el servicio perimetral de **acceso,** defina el **FQDN** del grupo para el servicio perimetral de acceso tal como se define en DNS por host (A y AAAA si se usa IPv6) y un valor de puerto
    
- Para editar el servicio perimetral de conferencia **web,** defina un **FQDN** de grupo para el servicio perimetral de conferencia web como se define en DNS por host (A y AAAA si se usa IPv6) y un valor de puerto
    
- Para editar el servicio perimetral **A/V,** se define un **FQDN** de grupo para el servicio perimetral A/V como se define en DNS por host (A y AAAA si se usa IPv6) y un valor de puerto
    
    > [!IMPORTANT]
    > Si ha seleccionado la casilla Habilitar fqdn y dirección IP independientes para conferencias web y **A/V,** solo el FQDN del grupo de servidores perimetrales de acceso estará disponible para su edición. Asigne puertos distintos para cada uno de los tres servicios perimetrales.
  
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  

