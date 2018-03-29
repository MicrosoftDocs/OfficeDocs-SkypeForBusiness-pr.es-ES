---
title: Editar borde configuración Expander para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Edite la configuración para el servidor perimetral o un grupo de servidores de borde mediante la configuración de las propiedades siguientes:'
ms.openlocfilehash: 682412e1a486cc7351f081d903d8db1131367623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar borde configuración Expander para Lync Server 2010
 
Edite la configuración para el servidor perimetral o un grupo de servidores de borde mediante la configuración de las propiedades siguientes: 
  
 **General**
  
- **FQDN del grupo interno**: el nombre de dominio completo interno del grupo es la identidad del servidor perimetral o la piscina de borde tal como se define en el registro de host (A o AAAA para IPv6) (DNS) del sistema de nombres de dominio.
    
- Si desea habilitar el servidor perimetral o un grupo de servidores de borde para la federación con otros socios de protocolo de inicio de sesión, seleccione **Habilitar la federación para este grupo de borde (puerto 5061)** .
    
    > [!IMPORTANT]
    > Sólo puede definir un servidor perimetral o grupo de servidores de borde activamente para la federación. La configuración mostrada en la captura de pantalla asociada indica que otro grupo de servidor perimetral o borde ya está configurado para la federación. El registro SRV de DNS externo para la federación (_sipfederationtls._tcp.\< nombre de dominio externo\>) elija el servidor perimetral o un grupo de servidores de borde para la federación. 
  
- El **Puerto interno de replicación de configuración (HTTPS)**, en el puerto TCP 4443, de forma predeterminada es el puerto que el local (es decir, local para los servidores perimetrales) copia del almacén de Administración Central se replica a través de. La copia local del almacén de Administración Central está en la base de datos **RTCLOCAL** en el SQL Server en cada equipo. La replicación es unidireccional, iniciadas desde el servidor de Administración Central (o el grupo de servidor Front-End o Front-End que desempeña la función de servidor de Administración Central) para los servidores perimetrales y es un puerto de la interfaz interna.
    
 **Selección de salto siguiente**
  
- Seleccione de la lista de su **grupo de salto siguiente**. Definir Director, grupo de directores, grupo de servidor Front-End o Front-End para asumir esta función. El siguiente grupo de salto es el servidor o grupo de servidores que se aceptará los mensajes SIP entrantes desde el servidor perimetral o interfaz interna de agrupación de borde y enviar salida SIP a la interfaz interna del borde.
    
    > [!NOTE]
    > El Director es una función opcional y si se decide no implementar directores, los servidores frontales (único equipo o grupo) asumirá la función de Director. 
  
 **Configuración externa**
  
Esta sección de las propiedades permite editar las propiedades de la configuración del servidor de borde o fondo de borde externa. Pueden modificarse las siguientes propiedades:
  
- Seleccione el **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** nombres de casilla de verificación si desea asignar distintas direcciones IP y nombre de dominio completo para cada servicio del servidor perimetral.
    
    > [!NOTE]
    > Si decide no activar la casilla de verificación, debe utilizar puertos independientes para cada servicio de borde. Cada servicio de borde compartirá el FQDN definido para el servicio de servidor perimetral de acceso y, por tanto, se utilizará la misma dirección IP. Cada servicio de borde debe identificarse de forma exclusiva por una dirección IP distinta y mismo puerto, o bien la misma dirección IP y los valores de puerto único. 
  
- Seleccione **A / servicio V perimetral es NAT habilitado** si desea configurar el A / V borde de servicio para utilizar una dirección privada o en otra dirección en la que se oculta detrás de un dispositivo de traducción (NAT) de dirección de red.
    
- Para editar el **servicio acceso perimetral**, definir el **FQDN del grupo de servidores** para el servicio de servidor perimetral de acceso tal como se define en DNS host (A y AAAA si se utiliza IPv6) registros y un valor de puerto
    
- Para editar el **servicio perimetral de conferencia Web**, definir un **Pool FQDN** para el servicio perimetral de conferencia Web tal como se define en DNS host (A y AAAA si se utiliza IPv6) registros y un valor de puerto
    
- Para modificar el **A / servicio perimetral V**, definir un **Pool FQDN** en lugar de A / V borde servicio tal como se define en DNS host (A y AAAA si se utiliza IPv6) registros y un valor de puerto
    
    > [!IMPORTANT]
    > Si ha seleccionado la **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** casilla de verificación, el servicio de servidor perimetral de acceso Pool FQDN estará disponible para su edición. Asignar puertos distintos para cada uno de los tres servicios de borde.
  
 **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
 **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
 **Ayuda** Abre esta pantalla de ayuda.
  

