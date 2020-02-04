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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Para editar la configuración del servidor perimetral o del grupo Edge, configure las siguientes propiedades:'
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697385"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar expansor de configuración perimetral para Lync Server 2010
 
Para editar la configuración del servidor perimetral o del grupo Edge, configure las siguientes propiedades: 
  
 **General**
  
- **FQDN del grupo interno**: el nombre de dominio completo del grupo interno es la identidad del servidor perimetral o del grupo de servidores perimetrales según se define en el registro del sistema de nombres de dominio (DNS) (a o AAAA para IPv6).
    
- Seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)** si desea habilitar el servidor perimetral o el grupo perimetral para la Federación con otros socios del Protocolo de inicio de sesión.
    
    > [!IMPORTANT]
    > Solo puede definir un servidor perimetral o un grupo perimetral de forma activa para la Federación. La configuración que se muestra en la captura de pantalla asociada indica que ya está configurado otro servidor perimetral o un grupo perimetral para la Federación. El registro SRV de DNS externo para la Federación (_sipfederationtls.\< _tcp. nombre\>de dominio externo) apuntará al servidor perimetral o al grupo perimetral para la Federación. 
  
- El **Puerto de replicación de configuración interna (https)**, de forma predeterminada en el puerto TCP 4443, es el puerto por el que se replica la copia local (es decir, local de los servidores perimetrales) del almacén central de administración. La copia local del almacén de administración central está en la base de datos **RTCLOCAL** en SQL Server en cada equipo. La replicación es unidireccional, iniciada desde el servidor de administración central (o, el servidor front-end o el grupo de servidores front-end que tiene el rol de servidor de administración central) en los servidores perimetrales y es un puerto de interfaz interna.
    
  **Selección del próximo salto**
  
- Seleccione la lista de su **grupo de próximos saltos**. Defina un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end para asumir este rol. El siguiente grupo de saltos es el servidor o grupo de servidores que aceptará mensajes SIP entrantes de la interfaz interna del servidor perimetral o de la agrupación perimetral y enviar SIP saliente a la interfaz interna de Edge.
    
    > [!NOTE]
    > El director es un rol opcional y si decide no implementar directores, los servidores front-end (un equipo o un grupo) asumirán el rol de director. 
  
  **Configuración externa**
  
Esta sección de las propiedades le permite editar las propiedades de la configuración externa del servidor perimetral o del grupo Edge. Pueden modificarse las siguientes propiedades:
  
- Seleccione las casillas de verificación **Habilitar FQDN e dirección IP para las conferencias web y a/V** si desea asignar direcciones IP y nombres de dominio completos para cada servicio de servidor perimetral.
    
    > [!NOTE]
    > Si decide no activar la casilla, debe usar puertos independientes para cada servicio perimetral. Cada servicio perimetral compartirá el FQDN definido para el servicio perimetral de acceso y, por lo tanto, usará la misma dirección IP. Cada servicio perimetral debe estar identificado de forma exclusiva por una dirección IP distinta y el mismo puerto, o por la misma dirección IP y valores de Puerto únicos. 
  
- Seleccione el **servicio de borde a/v es NAT habilitado** si desea configurar el servicio perimetral a/v para que use una dirección privada u otra dirección que se ocultará detrás de un dispositivo de traducción de direcciones de red (NAT).
    
- Para editar el **servicio perimetral de acceso**, define el **FQDN del grupo** de servidores para el servicio perimetral de acceso según se define en DNS por host (a y AAAA si se usa IPv6) y un valor de Puerto
    
- Para editar el **servicio perimetral de conferencias web**, define un **FQDN de grupo** para el servicio perimetral de conferencias web definido en DNS por host (a y AAAA si se usa IPv6) y un valor de Puerto
    
- Para editar el **servicio perimetral a/v**, define un **FQDN de grupo** para el servicio perimetral a/v definido en DNS por host (a y AAAA si se usa IPv6) y un valor de Puerto
    
    > [!IMPORTANT]
    > Si ha seleccionado las casillas de verificación **habilitar diferentes FQDN e IP para conferencias web y a/V** , solo el FQDN del grupo de servicio perimetral de acceso estará disponible para su edición. Asigne puertos distintos para cada uno de los tres servicios perimetrales.
  
  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda** Abre esta pantalla de ayuda.
  

