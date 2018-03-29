---
title: Definir troncos adicionales en el Generador de topologías en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumen: Conozca cómo definir un tronco adicional entre un servidor de mediación y una puerta de enlace, del mismo nivel en el generador de topología en Skype para Business Server 2015.'
ms.openlocfilehash: 67d378a794ed6a80b5721f9eb2e9e988ee4db048
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a>Definir troncos adicionales en el Generador de topologías en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a definir un tronco adicional entre un servidor de mediación y una puerta de enlace, del mismo nivel en el generador de topología en Skype para Business Server 2015.
  
Siga estos pasos para definir un tronco adicional a la que se puede asociar a un interlocutor con un servidor de mediación. Un interlocutor proporciona a los usuarios habilitados para Telefonía IP empresarial con conectividad a la red telefónica pública conmutada (PSTN). Un par puede ser una puerta de enlace RTC, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).
  
Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace.
  
> [!NOTE]
> Este tema se supone que tiene el programa de instalación de una puerta de enlace PSTN y tronco de raíz con al menos un independiente o colocadas mediación o grupo de servidores tal como se describe en [definir una puerta de enlace en el generador de topología en Skype para el año 2015 de Business Server](define-a-gateway.md) en la documentación de implementación.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir un tronco adicional entre un servidor de mediación y un interlocutor de puerta de enlace

1. Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. En Skype para Business Server, el nombre del sitio, los **Componentes compartidos**, haga clic en el nodo de **troncos** y, a continuación, haga clic en **Nuevo tronco**.
    3. En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco. Dos troncos no pueden tener el mismo nombre.
    
    > [!NOTE]
    > Si especifica Transport Layer Security (TLS) como el tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación. 
  
4. En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.
    5. En **Puerto de escucha para la puerta de enlace PSTN**, escriba el puerto de escucha que el interlocutor (puerta de enlace PSTN, IP-PBX o SBC) recibirá mensajes SIP desde el servidor de mediación que va a ser asociado con este tronco. Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS). Los puertos del dispositivo de sucursal que sobreviven predeterminados son 5081 para TCP y 5082 para TLS.
    
6. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.
    
    > [!NOTE]
    > Por razones de seguridad, se recomienda encarecidamente que implementa a un interlocutor en el servidor de mediación que pueden usar TLS. 
  
7. En **Servidor de mediación asociado**, seleccione el grupo de servidor de mediación para asociar con el tronco de raíz de este punto
    
8. En **puerto de servidor de mediación asociada**, escriba el puerto de escucha que el servidor de mediación recibirá mensajes SIP del interlocutor.
    
    > [!NOTE]
    > Compatible con varios tronco en Skype para Business Server, no se puede configurar dos troncos con nombres de tronco diferentes con el mismo **puerto del servidor de mediación asociado** y el **Puerto de escucha para la puerta de enlace IP/PSTN**
  
    > [!NOTE]
    > Compatible con varios tronco en Skype para Business Server, puede definirse varios SIP señalización de puertos en el servidor de mediación para la comunicación con varios homólogos. Al definir un tronco, debe ser el número de **puerto del servidor de mediación asociado** dentro del intervalo de puertos de escucha del protocolo respectivos permitidos por el servidor de mediación. Este intervalo de puerto se define en Skype para Business Server y el servidor de mediación. Haga clic en el grupo de servidor de mediación correspondiente y seleccione **Editar propiedades**. Especifique el intervalo de puertos en el campo **Puertos de escucha**.
  
9. Haga clic en **Aceptar**. 
    

