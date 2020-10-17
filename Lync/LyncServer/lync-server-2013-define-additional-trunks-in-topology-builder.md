---
title: 'Lync Server 2013: definir troncos adicionales en el generador de topologías'
description: 'Lync Server 2013: definir troncos adicionales en el generador de topologías.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57983d3e4d6a47c14f2dcdc153fe6872a33eb6e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567566"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Definir troncos adicionales en el generador de topologías de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Siga estos pasos para usar el generador de topologías para definir un tronco adicional al que puede asociar un *interlocutor* con un servidor de mediación. Un par proporciona a los usuarios habilitados para telefonía IP empresarial con conectividad a la red telefónica conmutada (RTC). Un punto puede ser una puerta de enlace PSTN, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP). El tronco define esta conexión entre el servidor de mediación y el interlocutor. Se pueden definir varios troncos por servidor de mediación. Se puede asociar un servidor de mediación con varios elementos del mismo nivel.

Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace identificada de forma única por la tupla:

{FQDN del servidor de mediación, Puerto de escucha del servidor de mediación (TLS o TCP): IP de puerta de enlace y FQDN, Puerto de escucha de la puerta de enlace}

<div>


> [!NOTE]  
> En este tema se supone que tiene configurado una puerta de enlace RTC y un tronco raíz con al menos un servidor o grupo de servidores de mediación combinado o independiente, tal y como se describe en <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir una puerta de enlace en el generador de topologías de Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>


> [!NOTE]  
> En este tema se supone que ha configurado al menos un grupo de servidores front-end o un servidor Standard Edition en un sitio central como mínimo, tal como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> , en la documentación de implementación.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir un tronco adicional entre un servidor de mediación y una puerta de enlace del mismo nivel

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En Lync Server 2013, su nombre de sitio, **componentes compartidos**, haga clic con el botón secundario en el nodo **troncos** y, a continuación, haga clic en **nuevo tronco**.
    
    ![Pantalla de estructura de archivo del generador de topologías de Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Pantalla de estructura de archivo del generador de topologías de Lync Server")

3.  En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco. Dos troncos no pueden tener el mismo nombre.
    
    <div>
    

    > [!NOTE]  
    > Si especifica seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del par del servidor de mediación.

    
    </div>

4.  En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.
    
    ![Configuración de propiedades del interlocutor de puerta de enlace RTC para tronco](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Configuración de propiedades del interlocutor de puerta de enlace RTC para tronco")

5.  En **Puerto de escucha para la puerta de enlace RTC**, escriba el puerto de escucha que el interlocutor (puerta de enlace RTC, IP-PBX o SBC) recibirá los mensajes SIP del servidor de mediación que se va a asociar a este tronco. Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS). Los puertos de aplicación de sucursal con funciones de supervivencia predeterminadas son 5081 para TCP y 5082 para TLS.

6.  En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de seguridad, se recomienda encarecidamente implementar un par en el servidor de mediación que pueda usar TLS.

    
    </div>

7.  En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación que se va a asociar con el tronco raíz de este punto.

8.  En **Puerto del servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación recibirá los mensajes SIP del homólogo.
    
    <div>
    

    > [!NOTE]  
    > Con el soporte de varios tronco en Lync Server 2013, no se pueden configurar dos troncos con nombres de tronco distintos con el mismo <STRONG>Puerto de servidor de mediación asociado</STRONG> y <STRONG>Puerto de escucha para la puerta de enlace IP/RTC</STRONG> .

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Con la compatibilidad con varios tronco en Lync Server 2013, se pueden definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varios elementos del mismo nivel. Al definir un tronco, el número de <STRONG>Puerto del servidor de mediación asociado</STRONG> debe estar dentro del intervalo de puertos de escucha para el protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en Lync Server 2013 y grupos de servidores de mediación. Haga clic con el botón secundario en el grupo de servidores de mediación correspondiente y seleccione <STRONG>Editar propiedades</STRONG>. Especifique el intervalo de puertos en el campo <STRONG>Puertos de escucha</STRONG>.

    
    </div>

9.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Modificar un tronco en el generador de topologías en Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

