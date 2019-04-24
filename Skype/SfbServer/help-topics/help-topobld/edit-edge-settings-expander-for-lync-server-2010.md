---
title: Editar expansor de configuración perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Modificar la configuración para el servidor perimetral o grupo de servidores perimetrales mediante la configuración de las siguientes propiedades:'
ms.openlocfilehash: a4ad88aa6ff565ac7c1ebb5134d476d34625418f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203133"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar expansor de configuración perimetral para Lync Server 2010
 
Modificar la configuración para el servidor perimetral o grupo de servidores perimetrales mediante la configuración de las siguientes propiedades: 
  
 **General**
  
- **FQDN del grupo de servidores interno**: el nombre de dominio completo del grupo de servidores interno es la identidad del servidor perimetral o grupo de servidores perimetrales como se define en el registro de host (A o AAAA para IPv6) (DNS) del sistema de nombres de dominio.
    
- Seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** si desea habilitar el servidor perimetral o grupo de servidores perimetrales para la federación con otros socios de protocolo de inicio de sesión.
    
    > [!IMPORTANT]
    > Sólo se puede definir un servidor perimetral o grupo de servidores perimetrales activamente para la federación. La configuración que se muestra en la captura de pantalla asociada indica que otro servidor perimetral o grupo perimetral ya está configurado para la federación. El registro SRV de DNS externo para la federación (_sipfederationtls._tcp.\< nombre de dominio externo\>) seleccione el servidor perimetral o grupo de servidores perimetrales para la federación. 
  
- El **Puerto de replicación de configuración interna (HTTPS)**, de forma predeterminada en el puerto TCP 4443, es el puerto que el equipo local (es decir, local a los servidores perimetrales) copia del almacén de Administración Central se replica a través de. La copia local del almacén de Administración Central se encuentra en la base de datos **RTCLOCAL** en SQL Server en cada equipo. La replicación es unidireccional, iniciada desde el servidor de Administración Central (o el grupo de servidores Front-End o de servidor Front-End que contiene el rol de servidor de Administración Central) a los servidores perimetrales y es un puerto de la interfaz interna.
    
  **Selección de próximo salto**
  
- Seleccione el **grupo del próximo salto**para la lista. Definir Director, grupo de servidores Director, servidor Front-End o Front-End del grupo de servidores para adoptar esta función. El próximo salto es el servidor o grupo de servidores que se aceptará los mensajes SIP entrantes desde el servidor perimetral o interfaz interna del grupo de servidores perimetrales y envío saliente SIP a la interfaz interna perimetral.
    
    > [!NOTE]
    > El Director es un rol opcional y si decide no implementar directores, servidores de Front-End (un solo equipo o grupo de servidores) asumirá el rol de Director. 
  
  **Configuración de externo**
  
En esta sección de las propiedades permite editar las propiedades de la configuración externa del servidor perimetral o grupo de servidores perimetrales. Pueden modificarse las siguientes propiedades:
  
- Seleccione el **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** nombres de casilla de verificación si desea asignar distintas direcciones IP y nombre de dominio completo para cada servicio del servidor perimetral.
    
    > [!NOTE]
    > Si opta por no active la casilla de verificación, debe utilizar puertos distintos para cada servicio perimetral. Cada servicio perimetral compartirá el FQDN definido para el servicio de servidor perimetral de acceso y, por lo tanto, usará la misma dirección IP. Cada servicio perimetral debe identificarse de forma exclusiva por una dirección IP distinta y mismo puerto, o bien la misma dirección IP y los valores de puerto únicos. 
  
- Seleccione **A / servicio perimetral A/v está habilitado para NAT** si desea configurar el servicio perimetral A/v para usar una dirección privada u otra dirección que va a estar oculta detrás de un dispositivo (NAT) de la traducción de direcciones de red.
    
- Para editar el **servicio perimetral de acceso**, definir el **FQDN del grupo de servidores** para el servicio de servidor perimetral de acceso tal como se define en DNS por parte de host (A y AAAA si se utiliza IPv6) registros y un valor de puerto
    
- Para editar el **servicio perimetral de conferencia Web**, definir un **FQDN del grupo de servidores** para el servicio perimetral de conferencia Web como se define en DNS por parte de host (A y AAAA si se utiliza IPv6) registros y un valor de puerto
    
- Para editar la **A / servicio perimetral A/v**, definir un **FQDN del grupo de servidores** para el servicio perimetral A/v tal como se define en DNS por parte de host (A y AAAA si se utiliza IPv6) registros y un valor de puerto
    
    > [!IMPORTANT]
    > Si ha seleccionado la **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** casilla de verificación, el servicio de servidor perimetral de acceso FQDN del grupo estará disponible para su edición. Asignar puertos distintos para cada uno de los tres servicios perimetrales.
  
  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda** Abre esta pantalla de ayuda.
  

