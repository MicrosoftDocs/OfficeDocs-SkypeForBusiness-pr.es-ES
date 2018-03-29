---
title: Definir una puerta de enlace en el Generador de topologías en Skype Empresarial Server 2015
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumen: Conozca cómo definir una puerta de enlace PSTN en el generador de topología en Skype para Business Server 2015.'
ms.openlocfilehash: 7fa7f95fd04cf491dad32b0ab6cc050c5ebb0b0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a>Definir una puerta de enlace en el Generador de topologías en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a definir una puerta de enlace PSTN en el generador de topología en Skype para Business Server 2015.
  
Siga estos pasos para utilizar el generador de topología para definir un elemento del mismo nivel con el que se puede asociar un servidor de mediación para proporcionar conectividad a la red telefónica pública conmutada (PSTN) para los usuarios habilitados para Telefonía IP empresarial. Un interlocutor para el servidor de mediación puede ser una puerta de enlace PSTN, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicio de telefonía de Internet (ITSP) al que se conecta mediante la configuración de un troncal SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir un par para el servidor de mediación

1. Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. En Skype para Business Server, el nombre del sitio, los componentes compartidos, haga clic en el nodo de **Puertas de enlace PSTN** y, a continuación, haga clic en **Nueva puerta de enlace PSTN**.
3. En **Definir nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.
    
    > [!NOTE]
    > Si especifica Transport Layer Security (TLS) como el tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación. 
  
4. Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.

5. Definir un tronco de raíz para la puerta de enlace PSTN. Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace que se identifica por la tupla.
    
    {FQDN del servidor de mediación, puerto de escucha de servidor de mediación (TLS o TCP): puerta de enlace IP y FQDN, puerto de escucha de puerta de enlace}
    
     - Al definir una puerta de enlace PSTN en el generador de topología, debe definir un tronco raíz para agregar correctamente la puerta de enlace PSTN a la topología.
    
     - El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.
    
6. En **Puerto de escucha para la puerta de enlace IP/PSTN**, escriba el puerto de escucha que se va a utilizar la puerta de enlace, PBX o SBC para mensajes SIP desde el servidor de mediación se asociará con el tronco de raíz de la puerta de enlace PSTN. (De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control [TCP] y 5067 para la Seguridad de la capa de transporte [TLS] en una puerta de enlace RTC, PBX o SBC. En un dispositivo de sucursal que sobreviven en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS).
    
7. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]
    > Por razones de seguridad, se recomienda encarecidamente que implementa a un interlocutor en el servidor de mediación que pueden usar TLS. 
  
8. En **Servidor de mediación asociado**, seleccione el grupo de servidor de mediación para asociar con el tronco de raíz de esta puerta de enlace PSTN.
    
9. En **puerto de servidor de mediación asociada**, escriba el puerto de escucha que se va a utilizar el servidor de mediación para los mensajes desde la puerta de enlace SIP.
    
    > [!NOTE]
    > Compatible con varios tronco en Skype para Business Server, puede definir varios puertos en el servidor de mediación para la comunicación con varias puertas de enlace de RTC de señalización de SIP. Al definir un tronco, debe ser el **puerto del servidor de mediación asociado** dentro del intervalo de puertos de escucha del protocolo respectivos permitidos por el servidor de mediación. Este intervalo de puerto se define en Skype para Business Server y grupos de mediación. Haga clic en el grupo de servidor de mediación de interés y seleccione **Editar propiedades**. Especifique el intervalo de puertos en el campo **Puertos de escucha**.
  
10. Asegúrese de que el par definido está en ejecución y usa el FQDN o la dirección IP que ha especificado. A continuación, haga clic en **Finalizar**
    
11. Haga clic con el botón derecho en el nodo **Skype Empresarial Server** y, luego, haga clic en **Publicar topología**.
    

