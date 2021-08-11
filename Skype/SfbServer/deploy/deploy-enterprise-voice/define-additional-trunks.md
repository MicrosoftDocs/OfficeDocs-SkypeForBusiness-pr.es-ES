---
title: Definir troncos adicionales en el Generador de topologías en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Summary: Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype Empresarial Server.'
ms.openlocfilehash: 5c6863b93de0e8cf96ae2fa521da8dcd4b75c836d70d1d22d734ef25a21d6568
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283832"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definir troncos adicionales en el Generador de topologías en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo definir un tronco adicional entre un servidor de mediación y un punto de puerta de enlace en el Generador de topologías en Skype Empresarial Server.
  
Siga estos pasos para definir un tronco adicional al que puede asociar un mismo nivel con un servidor de mediación. Un sistema del mismo nivel proporciona a los Telefonía IP empresarial con conectividad a la red telefónica conmutada (RTC). Un punto puede ser una puerta de enlace PSTN, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).
  
Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace.
  
> [!NOTE]
> En este tema se supone que ha configurado una puerta de enlace RTC y un tronco raíz con al menos un servidor o grupo de servidores de mediación local o independiente, tal como se describe en [Define a gateway in Topology Builder in Skype Empresarial Server](define-a-gateway.md) en la documentación de implementación.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir un tronco adicional entre un servidor de mediación y un punto de enlace

1. Iniciar generador de topologías: haga clic en Inicio **,** todos los **programas,** haga clic en **Skype Empresarial Server 2015** y, a continuación, haga clic en **Skype Empresarial Server 2015Topology Builder**.
    
2. En Skype Empresarial Server, el nombre del sitio, **Componentes compartidos**, haga clic con el botón secundario en el **nodo Troncos** y, a continuación, haga clic **en Nuevo tronco**.
   1. En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco. Dos troncos no pueden tener el mismo nombre.
    
      > [!NOTE]
      > Si especifica Seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del mismo nivel del servidor de mediación. 
  
3. En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.
    5. En Puerto de escucha para puerta de enlace **RTC**, escriba el puerto de escucha que el mismo nivel (puerta de enlace RTC, IP-PBX o SBC) recibirá mensajes SIP del servidor de mediación que se va a asociar a este tronco. Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS). Los puertos predeterminados de aplicación de sucursal con funciones de supervivencia son 5081 para TCP y 5082 para TLS.
    
4. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.
    
    > [!NOTE]
    > Por motivos de seguridad, le recomendamos encarecidamente que implemente un servidor del mismo nivel en el servidor de mediación que pueda usar TLS. 
  
5. En **Servidor de mediación asociado,** seleccione el grupo de servidores de mediación que desea asociar con el tronco raíz de este mismo nivel
    
6. En **Puerto del servidor de mediación** asociado , escriba el puerto de escucha que el servidor de mediación recibirá mensajes SIP del mismo nivel.
    
    > [!NOTE]
    > Con la compatibilidad con varios troncos en Skype Empresarial Server, dos troncos  con nombres de tronco diferentes no se pueden configurar con el mismo puerto de servidor de mediación asociado y puerto de escucha para la puerta de enlace **IP/RTC**
  
    > [!NOTE]
    > Con la compatibilidad con varios troncos Skype Empresarial Server, se pueden definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varios sistemas del mismo nivel. Al definir un tronco, **el** número de puerto del servidor de mediación asociado debe estar dentro del intervalo de puertos de escucha para el protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en Skype Empresarial Server y grupos de servidores de mediación. Haga clic con el botón secundario en el grupo de servidores de mediación correspondiente y seleccione **Editar propiedades**. Especifique el intervalo de puertos en el campo **Puertos de escucha**.
  
7. Haga clic en **Aceptar**. 
    

