---
title: 'Lync Server 2013: Definir una puerta de enlace en el Generador de topologías'
TOCTitle: Definir una puerta de enlace en el Generador de topologías
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48275095
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir una puerta de enlace en el Generador de topologías en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-04_

Siga estos pasos para usar Generador de topologías para definir un *par* que pueda asociarse a un Servidor de mediación para proporcionar conectividad a la red telefónica conmutada (RTC) para usuarios habilitados para Telefonía IP empresarial. Un par para el Servidor de mediación puede ser una puerta de enlace de una red telefónica conmutada (RTC), un sistema IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSC) al que se conecta mediante la configuración de un tronco SIP.


> [!NOTE]
> En este tema se supone que hay instalado al menos un Grupo de servidores front-end o Servidor Standard Edition interno como mínimo en un sitio central con un Servidor de mediación combinado o independiente, tal como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">Publicar la topología en Lync Server 2013</A> de la documentación sobre implementación. En este tema también se supone que se ha comprobado que la infraestructura cumple los requisitos previos recogidos en <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Requisitos previos de software para la telefonía IP empresarial en Lync Server 2013</A> y <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Requisitos previos de seguridad y configuración para telefonía IP empresarial en Lync Server 2013</A>.



## Definición de un par para el servidor de mediación

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En Lync Server 2013, su nombre de sitio, Componentes compartidos, haga clic con el botón secundario en **Puertas de enlace RTC** y luego haga clic en **Nueva puerta de enlace RTC**.
    
    ![Generador de topologías de Lync Server 2013](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "Generador de topologías de Lync Server 2013")

3.  En **Definir la nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.
    
    ![Puerta de enlace IP/RTC](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "Puerta de enlace IP/RTC")
    

    > [!NOTE]
    > Si especifica Seguridad de la capa de transporte (TLS) como tipo de transporte, especifique el FQDN en vez de la dirección IP del punto del Servidor de mediación.



4.  Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.
    
    ![Dirección IP](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "Dirección IP")

5.  Defina un *tronco raíz* para la nueva puerta de enlace RTC. Un tronco es una conexión lógica entre un Servidor de mediación y una puerta de enlace identificada únicamente por la tupla.
    
    {FQDN de Servidor de mediación, puerto de escucha Servidor de mediación (TLS o TCP): puerta de enlace IP y FQDN, puerto de escucha de la pasarela de enlace}
    
      - Al definir una puerta de enlace RTC en Generador de topologías, debe definir un tronco raíz para agregar correctamente la puerta de enlace RTC a la topología.
    
      - El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.
    
    ![Definir puerta de enlace: tronco raíz](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "Definir puerta de enlace: tronco raíz")

6.  En **Puerto de escucha de la puerta de enlace IP/RTC**, introduzca el puerto de escucha que usará la puerta de enlace, el PBX o el SBC para mensajes SIP del Servidor de mediación que se asociará con el tronco raíz de la puerta de enlace RTC. (De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control (TCP) y 5067 para la Seguridad de la capa de transporte (TLS) en una puerta de enlace RTC, PBX o SBC. En una Aplicación de sucursal con funciones de supervivencia de un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS).

7.  En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.
    

    > [!NOTE]
    > Por motivos de seguridad, recomendamos encarecidamente que implemente un punto para el Servidor de mediación que puede usar TLS.



8.  En **Servidor de mediación asociados**, seleccione el Grupo de servidores de mediación que se va a asociar con el tronco raíz de esta puerta de enlace RTC.

9.  En **Puerto Servidor de mediación asociado**, escriba el puerto de escucha que usará Servidor de mediación para mensajes SIP desde la puerta de enlace.
    

    > [!NOTE]
    > Con varios troncos admitidos en Lync Server 2013, se pueden definir varios puertos de señalización SIP en el Servidor de mediación para usarse para la comunicación con varias puertas de enlace RTC. Al definir un tronco, el <STRONG>Puerto de Servidor de mediación asociado</STRONG> debe estar dentro del intervalo de los puertos de escucha del respectivo protocolo permitido por el Servidor de mediación. Este intervalo de puertos se define en Lync Server 2013 y Grupos de servidores de mediación. Haga clic con el botón secundario en el Grupo de servidores de mediación que le interesa y seleccione <STRONG>Editar propiedades</STRONG>. Especifique el intervalo de puertos en el campo <STRONG>Puertos de escucha</STRONG>.



10. Haga clic en **Finalizar**.

> [!IMPORTANT]  
> Antes de finalizar este paso, asegúrese de que el par definido está en marcha y que usa el FQDN o la dirección IP que ha especificado.



A continuación, para agregar un par a la topología, siga los procedimientos descritos en [Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de implementación. Debe publicar la topología cada vez que use Generador de topologías para crear o modificar la topología con el fin de que se puedan utilizar los datos para instalar los archivos para los servidores que están ejecutando Lync Server.

## Vea también

#### Tareas

[Modificación de un tronco en el Generador de topologías en Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)

