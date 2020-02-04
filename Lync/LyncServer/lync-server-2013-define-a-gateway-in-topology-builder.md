---
title: 'Lync Server 2013: definir una puerta de enlace en el generador de topología'
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
ms.openlocfilehash: 18f257648ba24930eaab0d314e34178ffd67a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Definir una puerta de enlace en el generador de topología de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Siga estos pasos para usar el generador de topología para definir un *interlocutor* con el que pueda asociar un servidor de mediación para proporcionar conectividad a la red de telefonía pública conmutada (RTC) para los usuarios habilitados para telefonía IP empresarial. Un interlocutor al servidor de mediación puede ser una puerta de enlace PSTN, IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP) al que se conecta mediante la configuración de un tronco de SIP.

<div>


> [!NOTE]  
> En este tema se supone que ha configurado al menos un grupo de servidores front-end interno o un servidor Standard Edition en al menos un sitio central con un servidor de mediación colocada o independiente, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la documentación de implementación. En este tema también se presupone que ha verificado que su infraestructura cumple con los requisitos previos descritos en <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">requisitos de software para telefonía IP empresarial en Lync server 2013</A> y los <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">requisitos previos de seguridad y configuración de telefonía IP empresarial en Lync Server 2013</A>.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir un interlocutor para el servidor de mediación

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En Lync Server 2013, nombre del sitio, componentes compartidos, haga clic con el botón derecho en el nodo **puertas de enlace RTC** y, a continuación, haga clic en **nueva puerta de enlace RTC**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  En **Definir nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Si especifica la seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación.

    
    </div>

4.  Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Defina un *tronco raíz* para la nueva puerta de enlace RTC. Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace que se identifica de forma única por la tupla.
    
    {Media Server FQDN, Puerto de escucha del servidor de mediación (TLS o TCP): IP de puerta de enlace y FQDN, Puerto de escucha de la puerta de enlace}
    
      - Al definir una puerta de enlace RTC en el generador de topología, debe definir un tronco raíz para agregar correctamente la puerta de enlace RTC a su topología.
    
      - El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  En **Puerto de escucha para la puerta de enlace IP/RTC**, escriba el puerto de escucha que usará la puerta de enlace, PBX o SBC para los mensajes SIP del servidor de mediación que se asociará con el tronco raíz de la puerta de enlace RTC. (De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control [TCP] y 5067 para la Seguridad de la capa de transporte [TLS] en una puerta de enlace RTC, PBX o SBC. En un equipo de sucursales con la supervivencia en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS.

7.  En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Por razones de seguridad, le recomendamos encarecidamente que implemente un interlocutor en el servidor de mediación que pueda usar TLS.

    
    </div>

8.  En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de esta puerta de enlace RTC.

9.  En **Puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación usará para los mensajes SIP de la puerta de enlace.
    
    <div>
    

    > [!NOTE]  
    > Con varias compatibilidades troncales en Lync Server 2013, se pueden definir varios puertos de señalización SIP en el servidor de mediación para que se usen en la comunicación con varias puertas de enlace RTC. Al definir un tronco, el <STRONG>Puerto de servidor de mediación asociado</STRONG> debe estar dentro del intervalo de los puertos de escucha para el protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en Lync Server 2013 y en los grupos de mediación. Haga clic con el botón derecho en el grupo de servidores de mediación de interés y seleccione <STRONG>Editar propiedades</STRONG>. Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

10. Haga clic en **Finalizar**.

<div>


> [!IMPORTANT]  
> Antes de completar este paso, asegúrese de que el interlocutor que ha definido está ejecutándose y esté usando el FQDN o la dirección IP que especificó.



</div>

A continuación, para agregar el elemento del mismo nivel a la topología, siga los procedimientos que se describen en [publicar la topología de Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de implementación. Debe publicar su topología cada vez que use el generador de topologías para crear o modificar su topología, de modo que los datos se puedan usar para instalar los archivos de los servidores que ejecutan Lync Server.

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

