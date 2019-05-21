---
title: Definir más troncos en el generador de topología en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumen: Aprenda a definir un troncal adicional entre un servidor de mediación y una puerta de enlace del mismo nivel en el generador de topología de Skype empresarial Server.'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303315"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definir más troncos en el generador de topología en Skype empresarial Server
 
**Resumen:** Aprenda a definir un troncal adicional entre un servidor de mediación y una puerta de enlace del mismo nivel en el generador de topología de Skype empresarial Server.
  
Siga estos pasos para definir un enlace adicional al que pueda asociar un interlocutor con un servidor de mediación. Un interlocutor proporciona a los usuarios habilitados para telefonía IP empresarial con conectividad a la red de telefonía pública conmutada (RTC). Un par puede ser una puerta de enlace RTC, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).
  
Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace.
  
> [!NOTE]
> En este tema se supone que tiene configurado una puerta de enlace RTC y un tronco de raíz con al menos un servidor o grupo de mediación colocado o independiente, según se describe en [definir una puerta de enlace en el generador de topologías de Skype empresarial Server](define-a-gateway.md) en la documentación de implementación.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir un troncal adicional entre un servidor de mediación y un interlocutor de puerta de enlace

1. Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.
    
2. En Skype empresarial Server, el nombre de su sitio, **componentes**compartidos, haga clic con el botón secundario en el nodo **troncos** y luego haga clic en **nuevo tronco**.
   1. En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco. Dos troncos no pueden tener el mismo nombre.
    
      > [!NOTE]
      > Si especifica la seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación. 
  
3. En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.
    5. En **Puerto en escucha para la puerta de enlace RTC**, escriba el puerto de escucha que el interlocutor (puerta de enlace PSTN, IP-PBX o SBC) recibirá los mensajes SIP del servidor de mediación que se va a asociar con este tronco. Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS). Los puertos predeterminados de los equipos de las sucursales supervivientes son 5081 para TCP y 5082 para TLS.
    
4. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.
    
    > [!NOTE]
    > Por razones de seguridad, le recomendamos encarecidamente que implemente un interlocutor en el servidor de mediación que pueda usar TLS. 
  
5. En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de este punto de conexión.
    
6. En **Puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación recibirá los mensajes SIP del interlocutor.
    
    > [!NOTE]
    > Con la compatibilidad de varios troncales en Skype empresarial Server, no se pueden configurar dos troncos con diferentes nombres de tronco con el mismo **Puerto de servidor de mediación asociado** y **Puerto de escucha para la puerta de enlace IP/PSTN**
  
    > [!NOTE]
    > Con varias compatibilidades troncales en Skype empresarial Server, se pueden definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varios elementos del mismo nivel. Al definir un tronco, el número de **Puerto de servidor de mediación asociado** debe estar dentro del intervalo de los puertos de escucha para el protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en Skype empresarial Server y en los grupos de servidores de mediación. Haga clic con el botón derecho en el grupo de servidores de mediación y seleccione **Editar propiedades**. Specify the port range in the **Listening ports** field.
  
7. Haga clic en **Aceptar**. 
    

