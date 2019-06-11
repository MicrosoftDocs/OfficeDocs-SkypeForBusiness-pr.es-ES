---
title: 'Lync Server 2013: definir un servidor de mediación en el generador de topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Definir un servidor de mediación en el generador de topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-25_

Siga los pasos que se indican en este tema para usar el generador de topologías para definir un servidor de mediación independiente o un grupo que tenga un grupo de servidores front-end en un sitio para el que no implementó previamente la telefonía IP empresarial.

Puede definir una topología con una cuenta que sea miembro del grupo de administradores.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Definir un servidor de mediación con un grupo de servidores front-end

Siga los pasos que se indican en este tema para usar el generador de topologías para definir un servidor de mediación en un grupo de servidores front-end de un sitio donde no se haya implementado la telefonía IP empresarial.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para agregar un servidor de mediación a un grupo de servidores front-end

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un grupo de servidores front-end.

3.  En el árbol de consola, haga clic con el botón secundario en el tipo de grupo de servidores front-end que desee y, a continuación, haga clic en **nuevo grupo de servidores front-end.**..

4.  Avance por el asistente para **Definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados**.

5.  En **Seleccionar roles de servidor**colocados, active la opción servidor de mediación de **Collocate**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Si el tipo de grupo de front-end que seleccionó es Enterprise Edition, el componente de servidor de mediación se instalará en todos los servidores front-end de ese grupo de servidores front-end.</P>
    > <LI>
    > <P>El <STRONG>grupo de próximos saltos</STRONG> usado por el servidor de mediación será el grupo de servidores front-end en el que se encuentra el servidor de mediación.</P>
    > <LI>
    > <P>El <STRONG>Grupo perimetral</STRONG> usado por el servidor de mediación será el mismo grupo perimetral asociado al grupo de servidores front-end en el que se encuentra el servidor de mediación.</P></LI></UL>

    
    </div>

6.  Haga clic en **establecer como predeterminado** para usar este grupo de servidores front-end para enrutar llamadas desde Microsoft Office Communications Server 2007 R2 a la RTC.

7.  Haga clic en **Finalizar** cuando haya terminado de asociar uno o más elementos del mismo nivel al grupo de servidores front-end.
    
    <div>
    

    > [!NOTE]  
    > Antes de continuar con el siguiente paso del proceso de implementación de voz de empresa, asegúrese de que el grupo de servidores de mediación (es decir, el grupo front-end con el componente de servidor de mediación colocado) esté usando los FQDN que especificó.

    
    </div>

8.  Después, siga los procedimientos de la publicación de la [topología de Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de la guía de implementación para agregar el servidor de mediación a su topología antes de continuar con el siguiente paso de la modificación de los puertos de escucha del servidor de mediación, si es necesario. Debe publicar su topología cada vez que use el generador de topologías para definir o modificar su topología.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Definir un servidor de mediación independiente

Siga los pasos que se indican en este tema para usar el generador de topologías para definir un servidor de mediación o grupo de administradores independiente en un sitio en el que no se haya implementado la telefonía IP de forma previa.

Si ya ha implementado servidores de mediación colocados en grupos front-end en este sitio, puede omitir esta sección e [instalar los archivos de Media Server en Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) antes de continuar con la [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> En esta sección se supone que ya ha configurado al menos un grupo de servidores front-end, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la guía de implementación documentación.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>Para agregar un servidor de mediación

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el generador de topologías, en el árbol de consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.

3.  En el árbol de consola, haga clic con el botón derecho en el nodo de **grupos** de mediación y en **grupo de servidores**de mediación.

4.  En **definir nuevo grupo**de mediación, escriba el nombre de dominio completo (FQDN) del grupo de servidores de mediación.

5.  A continuación, siga uno de los procedimientos siguientes:
    
      - Si desea implementar varios servidores de mediación en el grupo para proporcionar alta disponibilidad, seleccione **varios grupos de equipos**.
        
        <div>
        

        > [!NOTE]  
        > Debe implementar el equilibrio de carga de DNS para admitir grupos de servidores de mediación que tengan varios servidores de mediación. Para obtener más información, vea la sección usar el equilibrio de carga de DNS en las agrupaciones de servidores de mediación de <A href="lync-server-2013-dns-load-balancing.md">equilibrio de carga de DNS en Lync Server 2013</A> en la documentación de planeación.

        
        </div>
    
      - Si desea implementar solo un servidor de mediación en el grupo porque no necesita alta disponibilidad, seleccione **grupo de equipos únicos**. Omita el paso siguiente.

6.  Si ha seleccionado **Grupo de varios equipos** en el paso anterior, en el elemento **Definir equipos de este grupo**, haga clic en **FQDN de equipo**, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en **Agregar**. Repita este paso para todos los demás servidores de mediación que desee agregar al grupo. Cuando haya definido todos los equipos del grupo, haga clic en **Siguiente**.

7.  En la página **seleccionar el próximo salto** , haga clic en **grupo de próximos saltos**, haga clic en el FQDN del grupo de servidores front-end que usará este grupo de servidores de mediación y, a continuación, haga clic en **siguiente**.

8.  En la página **Seleccionar un servidor perimetral**, realice una de las operaciones siguientes:
    
      - Si desea proporcionar conectividad RTC a usuarios externos habilitados para telefonía IP empresarial, en **Seleccionar grupo perimetral usado por este servidor**de mediación, haga clic en el FQDN del grupo de servidores perimetrales que usarán este grupo de servidores de mediación para proporcionar conectividad RTC a esos usuarios externos y, a continuación, haga clic en **siguiente**.
    
      - Si no tiene previsto habilitar usuarios externos para telefonía IP empresarial, o si no desea proporcionar conectividad RTC a los usuarios cuando se encuentren fuera de la red interna, haga clic en **siguiente**.

9.  Después, siga los procedimientos de la publicación de la [topología de Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de implementación para agregar el servidor de mediación a la topología. Debe publicar su topología cada vez que use el generador de topologías para crear o modificar su topología, de modo que los datos se puedan usar para instalar los archivos de los servidores que ejecutan Lync Server. Después, continúe con los pasos siguientes para modificar los puertos de escucha en el servidor de mediación, si es necesario.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Definir los puertos de escucha del servidor de mediación

Siga los pasos que se indican en este tema para usar el generador de topología para definir los puertos de escucha que un servidor de mediación o grupo aceptará las conexiones entrantes de una puerta de enlace del mismo nivel.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar los puertos de escucha del servidor de mediación

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el generador de topología, en el árbol de consola, expanda el nodo **grupos** de mediación y haga clic con el botón secundario en el servidor de mediación creado previamente.

3.  De forma predeterminada, los puertos de escucha SIP en el servidor de mediación son 5070 para el tráfico TLS desde Lync Server, 5067 para tráfico TLS de pares (gateways, PBXes o SBCs). El puerto TCP está deshabilitado de forma predeterminada. Debe habilitar el puerto TCP si tiene puertas de enlace que no son compatibles con TLS.

4.  Especifique el intervalo de puerto de escucha TLS o TCP que desee el servidor de mediación aceptará conexiones entrantes de puertas de enlace RTC.
    
    <div>
    

    > [!NOTE]  
    > No es necesario indicar este intervalo si no se ha seleccionado <STRONG>Habilitar puerto TCP</STRONG>. Este valor es opcional.

    
    </div>

Después, [defina una puerta de enlace en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e instale los archivos en cada servidor de mediación del grupo siguiendo los procedimientos de [instalar los archivos de Media Server en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

