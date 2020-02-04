---
title: 'Lync Server 2013: definir troncos adicionales en el generador de topología'
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
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Definir más troncos en el generador de topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Siga estos pasos para usar el generador de topología para definir un enlace adicional al que pueda asociar un *interlocutor* con un servidor de mediación. Un interlocutor proporciona a los usuarios habilitados para telefonía IP empresarial con conectividad a la red de telefonía pública conmutada (RTC). Un par puede ser una puerta de enlace RTC, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP). El tronco define esta conexión entre el servidor de mediación y el interlocutor. Se pueden definir varios troncos por servidor de mediación. Se puede asociar un servidor de mediación con varios elementos del mismo nivel.

Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace identificada de forma única por la tupla:

{Media Server FQDN, Puerto de escucha del servidor de mediación (TLS o TCP): IP de puerta de enlace y FQDN, Puerto de escucha de la puerta de enlace}

<div>


> [!NOTE]  
> En este tema se supone que tiene configurado una puerta de enlace PSTN y un tronco raíz con al menos un servidor o grupo de mediación de proviene o independiente, tal y como se describe en <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir una puerta de enlace en el generador de topología de Lync Server 2013</A> , en la documentación de implementación.



</div>

<div>


> [!NOTE]  
> En este tema se supone que ha configurado al menos un grupo de servidores front-end o un servidor Standard Edition en un sitio central como mínimo, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir un troncal adicional entre un servidor de mediación y un interlocutor de puerta de enlace

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En Lync Server 2013, nombre del sitio, **componentes compartidos**, haga clic con el botón derecho en el nodo **troncos** y, después, haga clic en **nuevo tronco**.
    
    ![Pantalla de estructura de archivos del generador de topología de Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Pantalla de estructura de archivos del generador de topología de Lync Server")

3.  En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco. Dos troncos no pueden tener el mismo nombre.
    
    <div>
    

    > [!NOTE]  
    > Si especifica la seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación.

    
    </div>

4.  En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.
    
    ![Configuración de propiedades para puerta de enlace RTC peer para troncal](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Configuración de propiedades para puerta de enlace RTC peer para troncal")

5.  En **Puerto en escucha para la puerta de enlace RTC**, escriba el puerto de escucha que el interlocutor (puerta de enlace PSTN, IP-PBX o SBC) recibirá los mensajes SIP del servidor de mediación que se va a asociar con este tronco. Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS). Los puertos predeterminados de los equipos de las sucursales supervivientes son 5081 para TCP y 5082 para TLS.

6.  En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.
    
    <div>
    

    > [!NOTE]  
    > Por razones de seguridad, le recomendamos encarecidamente que implemente un interlocutor en el servidor de mediación que pueda usar TLS.

    
    </div>

7.  En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de este punto de conexión.

8.  En **Puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación recibirá los mensajes SIP del interlocutor.
    
    <div>
    

    > [!NOTE]  
    > Con varias compatibilidades troncales en Lync Server 2013, no se pueden configurar dos troncos con diferentes nombres de tronco con el mismo <STRONG>Puerto de servidor de mediación asociado</STRONG> y <STRONG>Puerto de escucha para la puerta de enlace IP/PSTN</STRONG>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Con varias compatibilidades troncales en Lync Server 2013, se pueden definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varios elementos del mismo nivel. Al definir un tronco, el número de <STRONG>Puerto de servidor de mediación asociado</STRONG> debe estar dentro del intervalo de los puertos de escucha para el protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en Lync Server 2013 y en grupos de servidores de mediación. Haga clic con el botón derecho en el grupo de servidores de mediación y seleccione <STRONG>Editar propiedades</STRONG>. Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

9.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Modificar un tronco en el generador de topología en Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

