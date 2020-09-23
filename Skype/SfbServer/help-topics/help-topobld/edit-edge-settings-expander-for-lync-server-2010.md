---
title: Editar expansor de configuración perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Para editar la configuración del servidor perimetral o del grupo de servidores perimetrales, configure las siguientes propiedades:'
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216121"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar expansor de configuración perimetral para Lync Server 2010
 
Para editar la configuración del servidor perimetral o del grupo de servidores perimetrales, configure las siguientes propiedades: 
  
 **General**
  
- **FQDN del grupo**interno: el nombre de dominio completo del grupo de servidores interno es la identidad del servidor perimetral o del grupo de servidores perimetrales como se define en el registro del sistema de nombres de dominio (DNS) (A o AAAA para IPv6).
    
- Seleccione **Habilitar la Federación para este grupo de servidores perimetrales (puerto 5061)** si desea habilitar el servidor perimetral o el grupo de servidores perimetrales para la Federación con otros asociados del Protocolo de inicio de sesión.
    
    > [!IMPORTANT]
    > Solo puede definir un servidor perimetral o un grupo de servidores perimetrales de forma activa para la Federación. La configuración que se muestra en la captura de pantalla asociada indica que ya se ha configurado otro servidor perimetral o un grupo de servidores perimetrales para la Federación. El registro DNS SRV externo para la Federación (_sipfederationtls. _tcp. \<external domain name\> ) apuntará al servidor perimetral o al grupo de servidores perimetrales para la Federación. 
  
- De forma predeterminada, el puerto de **replicación de configuración (https) interno**en el puerto TCP 4443 es el puerto que ha replicado la copia local (es decir, local del servidor perimetral) del almacén de administración central. La copia local del almacén de administración central se encuentra en la base de datos de **RTCLOCAL** en SQL Server en cada equipo. La replicación es unidireccional, iniciada desde el servidor de administración central (o, el servidor front-end o el grupo de servidores front-end que tiene el rol de servidor de administración central) en los servidores perimetrales y es un puerto de interfaz interna.
    
  **Selección de próximo salto**
  
- Seleccione para la lista su grupo de servidores del **próximo salto**. Puede definir un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end para que asuma este rol. El grupo de servidores del próximo salto es el servidor o grupo de servidores que aceptará los mensajes SIP entrantes desde la interfaz interna del servidor perimetral o del grupo de servidores perimetrales, y enviará el SIP saliente a la interfaz perimetral interna.
    
    > [!NOTE]
    > El director es un rol opcional y, si decide no implementar los directores, los servidores front-end (un solo equipo o grupo) asumirán el rol de director. 
  
  **Configuración externa**
  
En esta sección de las propiedades se pueden editar las propiedades de la configuración externa del servidor perimetral o del grupo de servidores perimetrales. Pueden modificarse las siguientes propiedades:
  
- Active la casilla **habilitar diferentes FQDN y dirección IP para conferencia web y a/V** si desea asignar distintas direcciones IP y nombres de dominio completos a cada servicio del servidor perimetral.
    
    > [!NOTE]
    > Si opta por no seleccionar la casilla de verificación, debe usar puertos independientes para cada servicio perimetral. Cada servicio perimetral compartirá el FQDN que se ha definido para el servicio perimetral de acceso y, por lo tanto, usará la misma dirección IP. Cada servicio perimetral debe identificarse de forma exclusiva mediante una dirección IP distinta, el mismo puerto o la misma dirección IP y los valores de Puerto únicos. 
  
- Seleccione el **servicio perimetral a/v está habilitado para NAT** si desea configurar el servicio perimetral a/v para que use una dirección privada u otra dirección que se ocultará detrás de un dispositivo de traducción de direcciones de red (NAT).
    
- Para editar el **servicio perimetral de acceso**, defina el **FQDN del grupo** de servidores para el servicio perimetral de acceso tal y como se haya definido en DNS por los registros host (a y AAAA si se usa IPv6) y un valor de puerto.
    
- Para editar el **servicio perimetral de conferencia web**, defina un **FQDN de grupo** de servidores para el servicio perimetral de conferencia web definido en DNS por los registros de host (a y AAAA si se usa IPv6) y un valor de puerto.
    
- Para editar el **servicio perimetral a/v**, defina un **FQDN de grupo** de servidores para el servicio perimetral a/v, tal y como se define en DNS mediante registros de host (a y AAAA si se usa IPv6) y un valor de puerto.
    
    > [!IMPORTANT]
    > Si ha seleccionado la casilla **habilitar diferentes FQDN y dirección IP para conferencia web y a/V** , solo el FQDN del grupo de servicio perimetral de acceso estará disponible para su edición. Asignar puertos distintos para cada uno de los tres servicios perimetrales.
  
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  

