---
title: 'Lync Server 2013: definir una puerta de enlace en el generador de topologías'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f23ef91f7f0a6f1205f5f95326b8ebe58b66df4b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516497"
---
# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Definir una puerta de enlace en el generador de topologías de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Siga estos pasos para usar el generador de topologías para definir un *par* con el que pueda asociar un servidor de mediación para proporcionar conectividad a la red telefónica conmutada (RTC) para los usuarios habilitados para telefonía IP empresarial. Un par al servidor de mediación puede ser una puerta de enlace RTC, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP) al que se conecta mediante la configuración de un tronco SIP.

<div>


> [!NOTE]  
> En este tema se supone que ha configurado al menos un grupo de servidores front-end interno o un servidor Standard Edition en al menos un sitio central con un servidor de mediación combinado o independiente, tal como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la documentación sobre implementación. En este tema también se presupone que se ha comprobado que la infraestructura cumple con los requisitos previos descritos en <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">software Prerequisites for Enterprise Voice en Lync server 2013</A> y los <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">requisitos previos de seguridad y configuración para telefonía IP empresarial en Lync Server 2013</A>.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>Definición de un par para el servidor de mediación

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En Lync Server 2013, su nombre de sitio, componentes compartidos, haga clic con el botón secundario en el nodo **puertas de enlace RTC** y, a continuación, haga clic en **nueva puerta de enlace RTC**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  En **Definir la nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Si especifica seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del par del servidor de mediación.

    
    </div>

4.  Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Defina un *tronco raíz* para la nueva puerta de enlace RTC. Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace identificada de forma única por la tupla.
    
    {FQDN del servidor de mediación, Puerto de escucha del servidor de mediación (TLS o TCP): IP de puerta de enlace y FQDN, Puerto de escucha de la puerta de enlace}
    
      - Al definir una puerta de enlace RTC en el generador de topologías, debe definir un tronco raíz para agregar correctamente la puerta de enlace RTC a la topología.
    
      - El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  En **Puerto de escucha para la puerta de enlace IP/RTC**, escriba el puerto de escucha que usará la puerta de enlace, PBX o SBC para los mensajes SIP del servidor de mediación que se va a asociar al tronco raíz de la puerta de enlace RTC. (De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control (TCP) y 5067 para la Seguridad de la capa de transporte (TLS) en una puerta de enlace RTC, PBX o SBC. En una aplicación de sucursal con funciones de supervivencia en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS.)

7.  En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de seguridad, se recomienda encarecidamente implementar un par en el servidor de mediación que pueda usar TLS.

    
    </div>

8.  En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación que se va a asociar con el tronco raíz de esta puerta de enlace RTC.

9.  En **Puerto del servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación usará para los mensajes SIP de la puerta de enlace.
    
    <div>
    

    > [!NOTE]  
    > Con la compatibilidad con varios tronco en Lync Server 2013, se pueden definir varios puertos de señalización SIP en el servidor de mediación que se va a usar para la comunicación con varias puertas de enlace RTC. Al definir un tronco, el <STRONG>Puerto del servidor de mediación asociado</STRONG> debe estar en el intervalo de puertos de escucha del protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en Lync Server 2013 y los grupos de servidores de mediación. Haga clic con el botón secundario en el grupo de servidores de mediación de interés y seleccione <STRONG>Editar propiedades</STRONG>. Especifique el intervalo de puertos en el campo <STRONG>Puertos de escucha</STRONG>.

    
    </div>

10. Haga clic en **Finalizar**.

<div>


> [!IMPORTANT]  
> Antes de finalizar este paso, asegúrese de que el par definido está en marcha y que usa el FQDN o la dirección IP que ha especificado.



</div>

A continuación, para agregar el elemento del mismo nivel a la topología, siga los procedimientos descritos en [Publish The Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación sobre implementación. Debe publicar la topología cada vez que use el generador de topologías para crear o modificar la topología, de modo que los datos se puedan usar para instalar los archivos de los servidores que ejecutan Lync Server.

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

