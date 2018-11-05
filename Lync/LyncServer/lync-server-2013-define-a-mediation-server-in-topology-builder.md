---
title: "Lync Server 2013: Definir un servidor de mediación en el Generador de topologías"
TOCTitle: Definir un servidor de mediación en el Generador de topologías
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48275387
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir un servidor de mediación en el Generador de topologías en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-25_

Siga los pasos de este tema para usar el Generador de topologías para definir un Servidor de mediación independiente o un grupo combinado con un Grupo de servidores front-end en un sitio en el que no se haya implementado Telefonía IP empresarial anteriormente.

Puede definir una topología mediante una cuenta que sea miembro del grupo Administradores.

## Definir un Servidor de mediación combinado con un Grupo de servidores front-end

Siga los pasos de este tema para usar el Generador de topologías para definir un Servidor de mediación combinado con un Grupo de servidores front-end en un sitio en el que Telefonía IP empresarial no se ha implementado anteriormente.

## Para agregar un Servidor de mediación a un Grupo de servidores front-end

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En Generador de topologías, en el árbol de la consola, expanda el nombre del sitio para el que desea definir un Grupo de servidores front-end.

3.  En el árbol de consola, haga clic con el botón derecho en el tipo de Grupo de servidores front-end que desee y haga clic en **NuevoGrupo de servidores front-end..**.

4.  Avance por el asistente **Definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados**.

5.  En **Seleccionar roles de servidor combinados**, seleccione la opción **CombinarServidor de mediación**.
    

    > [!NOTE]
    > <UL>
    > <LI>
    > <P>En caso de que el tipo de Grupo de servidores front-end seleccionado sea Enterprise Edition, el componente de Servidor de mediación se instalará en todos los Servidores front-end de dicho Grupo de servidores front-end.</P>
    > <LI>
    > <P>El <STRONG>Grupo de servidores del próximo salto</STRONG> que el Servidor de mediación use será el Grupo de servidores front-end con el que Servidor de mediación se haya combinado.</P>
    > <LI>
    > <P>El <STRONG>Grupo de servidores perimetrales</STRONG> que el Servidor de mediación use será el mismo Grupo de servidores perimetrales asociado al Grupo de servidores front-end con el que Servidor de mediación se combina.</P></LI></UL>



6.  Haga clic en **Establecer como predeterminado** para usar este Grupo de servidores front-end para enrutar las llamadas procedentes de Microsoft Office Communications Server 2007 R2 hacia la RTC.

7.  Cuando haya terminado de asociar uno o más elementos del mismo nivel al Grupo de servidores front-end, haga clic en **Finalizar**.
    

    > [!NOTE]
    > Antes de continuar con el siguiente paso del proceso de implementación de Telefonía IP empresarial, asegúrese de que el grupo de servidores de tipo Servidor de mediación (es decir, el Grupo de servidores front-end con el componente de Servidor de mediación combinado) se esté ejecutando con el FQDN especificado.



8.  Después, siga los procedimientos descritos en la sección [Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) de la documentación de la guía de implementación para agregar el Servidor de mediación a la topología antes de avanzar al siguiente paso, que consiste en modificar los puertos de escucha del Servidor de mediación (en caso de que sea necesario). La topología debe publicarse cada vez que se use el Generador de topologías para definir o modificar la topología.

## Definir un Servidor de mediación independiente

Siga los pasos de este tema para usar el Generador de topologías para definir un Servidor de mediación independiente o un grupo en un sitio en el que Telefonía IP empresarial no se haya implementado anteriormente.

Si ya ha implementado Servidores de mediación combinados con Grupos de servidores front-end en este sitio, puede saltarse esta sección y la sección [Instalar los archivos del servidor de mediación en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) antes de avanzar a [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).


> [!NOTE]
> En esta sección se da por hecho que ya ha instalado al menos un Grupo de servidores front-end, tal y como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013</A> y en <A href="lync-server-2013-publish-the-topology.md">Publicar la topología en Lync Server 2013</A> en la documentación de la guía de implementación.



## Para agregar un servidor de mediación

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En Generador de topologías, en el árbol de la consola, expanda el nombre del sitio para el que desea definir un Servidor de mediación.

3.  En el árbol de consola, haga clic con el botón derecho en el nodo **Grupos de servidores de mediación** y, después, haga clic en **Grupo de servidores de mediación**.

4.  En **Definir nuevo grupo de servidores de mediación**, escriba el nombre de dominio completo (FQDN) del grupo de servidores de tipo Servidor de mediación.

5.  A continuación, siga uno de los procedimientos siguientes:
    
      - Si quiere implementar varios Servidores de mediación en el grupo de servidores para proporcionar una alta disponibilidad, seleccione **Grupo de varios equipos**.
        

        > [!NOTE]
        > Debe implementar un equilibrio de carga DNS para dar cabida a grupos de servidores de tipo Servidor de mediación que tengan varios Servidores de mediación. Para obtener información detallada, vea la sección sobre cómo usar el equilibrio de carga&nbsp;DNS en grupos de servidores de tipo Servidor de mediación del tema <A href="lync-server-2013-dns-load-balancing.md">Equilibrio de carga de DNS en Lync Server 2013</A>, en la documentación de planeación.

    
      - Si solo desea implementar un Servidor de mediación en el grupo porque no requiere alta disponibilidad, entonces seleccione **Grupo de servidores de un solo equipo** . Omita el paso siguiente.

6.  Si ha seleccionado **Grupo de varios equipos** en el paso anterior, haga clic en **FQDN de equipo** en el elemento **Definir los equipos de este grupo de servidores** , escriba el FQDN de cada servidor del grupo de servidores y, después, haga clic en **Agregar** . Repita este paso con el resto de los Servidores de mediación que quiera agregar al grupo. Una vez definidos todos los equipos del grupo, haga clic en **Siguiente** .

7.  En la página **Seleccionar el siguiente salto** , haga clic en **Grupo de servidores del próximo salto** , haga clic en el FQDN del grupo de servidores front-end que usará este grupo de servidores de Servidor de mediación y, finalmente, haga clic en **Siguiente** .

8.  En la página **Seleccionar un servidor perimetral**, realice una de las operaciones siguientes:
    
      - Si desea proporcionar conectividad con RTC a usuarios externos habilitados para Telefonía IP empresarial, en **Seleccione el grupo de servidores perimetrales que usará este servidor de mediación** , haga clic en el FQDN del grupo de servidores perimetrales que usará este grupo de servidores de tipo Servidor de mediación para proporcionar dicha conectividad con RTC. Después, haga clic en **Siguiente** .
    
      - Si no tiene previsto habilitar usuarios externos para Telefonía IP empresarial o si no desea proporcionar conectividad con RTC a los usuarios cuando estén fuera de la red interna, haga clic en **Siguiente** .

9.  A continuación, siga los procedimientos de [Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), en la documentación relativa a la implementación, para agregar el servidor de mediación a la topología. Debe publicar la topología cada vez que utilice el Generador de topologías para crear o modificar la topología con el fin de que se puedan utilizar los datos para instalar los archivos de los servidores que están ejecutando Lync Server. Prosiga con los pasos siguientes para modificar, si fuera necesario, los puertos de escucha del servidor de mediación.

## Definir los puertos de escucha de un Servidor de mediación

Siga los pasos de este tema para usar el Generador de topologías para definir los puertos de escucha de los que un Servidor de mediación o un grupo aceptará conexiones entrantes procedentes de una puerta de enlace del mismo nivel.

## Para modificar los puertos de escucha de un Servidor de mediación

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En el árbol de consola del Generador de topologías, expanda el nodo **Grupos de servidores de mediación** y haga clic con el botón secundario en el Servidor de mediación que creó antes.

3.  Los puertos de escucha SIP predeterminados del servidor de mediación son 5070 para el tráfico TLS procedente de Lync Server y 5067 para el tráfico TLS procedente de elementos del mismo nivel (puertas de enlace, PBX o SBC). El puerto TCP está deshabilitado de forma predeterminada; deberá habilitarlo si tiene puertas de enlace que no admiten TLS.

4.  Indique el intervalo de puertos de escucha TLS o TCP del que el Servidor de mediación aceptará conexiones entrantes procedentes de puertas de enlace RTC.
    

    > [!NOTE]
    > No es necesario indicar este intervalo si no se ha seleccionado <STRONG>Habilitar puerto TCP</STRONG> . Este valor es opcional.



Tras esto, siga los pasos que se explican en [Definir una puerta de enlace en el Generador de topologías en Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) y los procedimientos descritos en [Instalar los archivos del servidor de mediación en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) para instalar los archivos en cada Servidor de mediación del grupo.

