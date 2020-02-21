---
title: 'Lync Server 2013: definir un servidor de mediación en el generador de topologías'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 782491b0df1c8d2432a9b4c69240293ccc126e7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Definir un servidor de mediación en el generador de topologías de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-25_

Siga los pasos de este tema para usar el generador de topologías para definir un servidor de mediación independiente o un grupo combinado con un grupo de servidores front-end en un sitio en el que no implementó anteriormente la telefonía IP empresarial.

Puede definir una topología mediante una cuenta que sea miembro del grupo de administradores.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Definir un servidor de mediación combinado con un grupo de servidores front-end

Siga los pasos descritos en este tema para usar el generador de topologías para definir un servidor de mediación combinado con un grupo de servidores front-end en un sitio en el que no se ha implementado la telefonía IP empresarial anteriormente.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para agregar un servidor de mediación a un grupo de servidores front-end

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el generador de topologías, en el árbol de la consola, expanda el nombre del sitio para el que desea definir un grupo de servidores front-end.

3.  En el árbol de la consola, haga clic con el botón secundario en el tipo de grupo de servidores front-end que desee y, a continuación, haga clic en **nuevo grupo de servidores front-end..**.

4.  Desplácese por el asistente **definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados** .

5.  En **Seleccionar roles de servidor combinados**, Compruebe la opción **combinar servidor de mediación**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Si el tipo de grupo de servidores front-end que seleccionó es Enterprise Edition, el componente de servidor de mediación se instalará en todos los servidores front-end de ese grupo de servidores front-end.</P>
    > <LI>
    > <P>El grupo de servidores del <STRONG>próximo salto</STRONG> usado por el servidor de mediación será el grupo de servidores front-end en el que se encuentra el servidor de mediación.</P>
    > <LI>
    > <P>El <STRONG>grupo de servidores perimetrales</STRONG> usado por el servidor de mediación será el mismo grupo de servidores perimetrales asociado con el grupo de servidores front-end en el que se encuentra el servidor de mediación.</P></LI></UL>

    
    </div>

6.  Haga clic en **establecer como predeterminado** para usar este grupo de servidores front-end para enrutar las llamadas de Microsoft Office Communications Server 2007 R2 a la RTC.

7.  Haga clic en **Finalizar** cuando haya terminado de asociar uno o más elementos del mismo nivel con el grupo de servidores front-end.
    
    <div>
    

    > [!NOTE]  
    > Antes de continuar con el paso siguiente del proceso de implementación de Enterprise Voice, asegúrese de que el grupo de servidores de mediación (es decir, el grupo de servidores front-end con el componente de servidor de mediación combinado) esté usando los FQDN que especificó.

    
    </div>

8.  A continuación, siga los procedimientos que se describen en [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de la guía de implementación para agregar el servidor de mediación a la topología antes de continuar con el siguiente paso de la modificación de los puertos de escucha del servidor de mediación, si es necesario. Debe publicar la topología cada vez que use el generador de topologías para definir o modificar la topología.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Definir servidor de mediación independiente

Siga los pasos de este tema para usar el generador de topologías para definir un servidor o un grupo de servidores de mediación independiente en un sitio en el que no se haya implementado anteriormente la telefonía IP empresarial.

Si ya ha implementado servidores de mediación combinados en grupos de servidores front-end en este sitio, puede omitir esta sección e [instalar los archivos del servidor de mediación en Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) antes de continuar con la [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> En esta sección se presupone que ya ha configurado al menos un grupo de servidores front-end, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> , en la documentación de la guía de implementación.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>Para agregar un servidor de mediación

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el generador de topologías, en el árbol de la consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.

3.  En el árbol de la consola, haga clic con el botón secundario en el nodo grupos de servidores de **mediación** y haga clic en **grupo de servidores de mediación**.

4.  En **definir nuevo grupo de mediación**, escriba el nombre de dominio completo (FQDN) del grupo de servidores de mediación.

5.  A continuación, realice una de las siguientes acciones:
    
      - Si quiere implementar varios servidores de mediación en el grupo para proporcionar alta disponibilidad, seleccione **grupo de varios equipos**.
        
        <div>
        

        > [!NOTE]  
        > Debe implementar el equilibrio de carga de DNS para admitir grupos de servidores de mediación que tengan varios servidores de mediación. Para obtener más información, consulte la sección usar el equilibrio de carga de DNS en grupos de servidores de mediación de <A href="lync-server-2013-dns-load-balancing.md">equilibrio de carga de DNS en Lync Server 2013</A> en la documentación referente a la planeación.

        
        </div>
    
      - Si desea implementar un solo servidor de mediación en el grupo de servidores porque no necesita alta disponibilidad, seleccione **grupo de un solo equipo**. Omita el paso siguiente.

6.  Si seleccionó **Grupo** de servidores de varios equipos en el paso anterior, en el elemento **definir los equipos de este grupo** , haga clic en **FQDN de equipo**, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en **Agregar**. Repita este paso para todos los servidores de mediación que desee agregar al grupo. Cuando haya definido todos los equipos del grupo, haga clic en **siguiente**.

7.  En la página **seleccionar el próximo salto** , haga clic en grupo de servidores de **próximo salto**, haga clic en el FQDN del grupo de servidores front-end que usará este grupo de servidores de mediación y, a continuación, haga clic en **siguiente**.

8.  En la página **seleccionar un servidor perimetral** , realice una de las siguientes acciones:
    
      - Si desea proporcionar conectividad con RTC a los usuarios externos habilitados para telefonía IP empresarial, en **Seleccionar grupo de servidores perimetrales usado por este servidor de mediación**, haga clic en el FQDN del grupo de servidores perimetrales que usará este grupo de servidores de mediación para proporcionar conectividad con RTC a dichos usuarios externos y, a continuación, haga clic en **siguiente**.
    
      - Si no va a habilitar a los usuarios externos para telefonía IP empresarial o si no desea proporcionar conectividad con RTC a los usuarios cuando están fuera de la red interna, haga clic en **siguiente**.

9.  A continuación, siga los procedimientos que se describen en publicación de la [topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación sobre implementación para agregar el servidor de mediación a la topología. Debe publicar la topología cada vez que use el generador de topologías para crear o modificar la topología, de modo que los datos puedan usarse para instalar los archivos de los servidores que ejecutan Lync Server. A continuación, continúe con los pasos siguientes para modificar los puertos de escucha en el servidor de mediación, si es necesario.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Definir los puertos de escucha del servidor de mediación

Siga los pasos que se indican en este tema para usar el generador de topologías para definir los puertos de escucha que un servidor de mediación o un grupo de servidores aceptará conexiones entrantes de una puerta de enlace del mismo nivel.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar los puertos de escucha del servidor de mediación

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el generador de topologías, en el árbol de la consola, expanda el nodo grupos de servidores de **mediación** y haga clic con el botón secundario en el servidor de mediación creado previamente.

3.  De forma predeterminada, los puertos de escucha SIP en el servidor de mediación son 5070 para el tráfico TLS de Lync Server, 5067 para el tráfico TLS de pares (gateways, PBXes o SBC). El puerto TCP está deshabilitado de forma predeterminada. Debe habilitar el puerto TCP si tiene puertas de enlace que no admiten TLS.

4.  Especifique el intervalo de puertos de escucha TLS o TCP que desea que el servidor de mediación acepte conexiones entrantes de las puertas de enlace RTC.
    
    <div>
    

    > [!NOTE]  
    > No es necesario escribir un intervalo de puertos TCP si no se ha seleccionado <STRONG>Habilitar el puerto TCP</STRONG> . Este valor es opcional.

    
    </div>

A continuación, [defina una puerta de enlace en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e instale los archivos en cada servidor de mediación del grupo siguiendo los procedimientos descritos en [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

