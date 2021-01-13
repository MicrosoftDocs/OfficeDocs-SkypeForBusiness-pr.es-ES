---
title: Definir troncos adicionales en topology Builder en Skype Empresarial Server
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
description: 'Resumen: obtenga información sobre cómo definir un tronco adicional entre un servidor de mediación y una puerta de enlace del mismo nivel en topology Builder en Skype Empresarial Server.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837000"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definir troncos adicionales en topology Builder en Skype Empresarial Server
 
**Resumen:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.
  
Siga estos pasos para definir un tronco adicional al que puede asociar un sistema del mismo nivel con un servidor de mediación. Un sistema del mismo nivel proporciona usuarios habilitados para Telefonía IP empresarial con conectividad a la red telefónica conmutada (RTC). Un punto puede ser una puerta de enlace PSTN, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).
  
Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace.
  
> [!NOTE]
> En este tema se presupone que ha configurado una puerta de enlace RTC y un tronco raíz con al menos un servidor o grupo de servidores de mediación local o independiente, tal como se describe en Definir una puerta de enlace en [topology Builder en Skype Empresarial Server](define-a-gateway.md) en la documentación sobre implementación.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir un tronco adicional entre un servidor de mediación y una puerta de enlace del mismo nivel

1. Inicie el Generador de topologías: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Skype Empresarial **Server 2015Topology Builder.**
    
2. En Skype Empresarial Server, su nombre de sitio, **Componentes** **compartidos,** haga clic con el botón secundario en el nodo Troncos y, a continuación, haga clic **en Nuevo tronco.**
   1. En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco. Dos troncos no pueden tener el mismo nombre.
    
      > [!NOTE]
      > Si especifica Seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del mismo nivel del servidor de mediación. 
  
3. En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.
    5. En Puerto de escucha para la puerta de enlace RTC, escriba el puerto de escucha que el interlocutor (puerta de enlace RTC, IP-PBX o SBC) recibirá mensajes SIP del servidor de mediación que se asociará a este tronco. Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS). Los puertos predeterminados de aplicación de sucursal con funciones de supervivencia son 5081 para TCP y 5082 para TLS.
    
4. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.
    
    > [!NOTE]
    > Por motivos de seguridad, se recomienda encarecidamente implementar un sistema del mismo nivel en el servidor de mediación que pueda usar TLS. 
  
5. En **Servidor de mediación asociado,** seleccione el grupo de servidores de mediación que desea asociar con el tronco raíz de este sistema del mismo nivel.
    
6. En **el puerto del servidor de mediación** asociado, escriba el puerto de escucha en el que el servidor de mediación recibirá mensajes SIP del sistema del mismo nivel.
    
    > [!NOTE]
    > Con la compatibilidad con varios troncos en Skype Empresarial Server, dos  troncos con nombres de tronco diferentes no se pueden configurar con el mismo puerto de servidor de mediación asociado y puerto de escucha para la puerta de enlace **IP/RTC**
  
    > [!NOTE]
    > Con la compatibilidad con varios troncos en Skype Empresarial Server, se pueden definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varios sistemas del mismo nivel. Al definir un  tronco, el número de puerto del servidor de mediación asociado debe estar dentro del intervalo de puertos de escucha para el protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en los grupos de servidores de mediación y Skype Empresarial Server. Haga clic con el botón secundario en el grupo de servidores de mediación correspondiente y seleccione **Editar propiedades.** Especifique el intervalo de puertos en el campo **Puertos de escucha**.
  
7. Haga clic en **Aceptar**. 
    

