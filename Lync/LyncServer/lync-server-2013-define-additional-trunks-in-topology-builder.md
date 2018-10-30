---
title: "Lync Server 2013 : Déf. d’autres jonctions dans le Gestionnaire de topologies"
TOCTitle: Definir troncos adicionales en el Generador de topologías
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49889774
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir troncos adicionales en el Generador de topologías en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-04_

Siga estos pasos para usar Generador de topologías para definir un tronco adicional al que pueda asociar un *punto* con un Servidor de mediación. Un punto proporciona usuarios habilitados para Telefonía IP empresarial con conectividad con la red telefónica conmutada (RTC). Un punto puede ser una puerta de enlace PSTN, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP). El tronco define esta conexión entre el Servidor de mediación y el punto. Se pueden definir varios troncos por Servidor de mediación. Un Servidor de mediación puede asociarse a varios puntos.

Un tronco es una conexión lógica entre un Servidor de mediación y una puerta de enlace con identificación única efectuada mediante tupla:

{FQDN de Servidor de mediación, puerto de escucha Servidor de mediación (TLS o TCP): puerta de enlace IP y FQDN, puerto de escucha de la pasarela de enlace}


> [!NOTE]
> En este tema se presupone que ha instalado una puerta de enlace PSTN y un tronco raíz con, como mínimo, un Servidor de mediación o grupo de servidores, combinado o independiente, tal como se describe en <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Definir una puerta de enlace en el Generador de topologías en Lync Server 2013</A> en la documentación de implementación.




> [!NOTE]
> En este tema se presupone que ha configurado como mínimo un Grupo de servidores front-end o un Servidor Standard Edition en un sitio central como mínimo, tal como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">Publicar la topología en Lync Server 2013</A> en la documentación de implementación.



## Para definir un tronco adicional entre un Servidor de mediación y una puerta de enlace de mismo nivel

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En Lync Server 2013, el nombre de sitio, **Componentes compartidos** , haga clic con el botón secundario en el nodo **Troncos** y después en **Nuevo tronco** .
    
    ![Pantalla de la estructura de archivos del Generador de topologías de Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Pantalla de la estructura de archivos del Generador de topologías de Lync Server")

3.  En **Definir nuevo tronco** , escriba un nombre descriptivo para identificar con exclusividad el tronco. Dos troncos no pueden tener el mismo nombre.
    

    > [!NOTE]
    > Si especifica Seguridad de la capa de transporte (TLS) como tipo de transporte, especifique el FQDN en vez de la dirección IP del punto del Servidor de mediación.



4.  En **Puerta de enlace PSTN asociada** , seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.
    
    ![Configuración de propiedades para puertas de enlace RTC del mismo nivel para tronco](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Configuración de propiedades para puertas de enlace RTC del mismo nivel para tronco")

5.  En el **Puerto de escucha para la puerta de enlace PSTN** , escriba el puerto de escucha en el que el punto (puerta de enlace PSTN, IP-PBX o SBC) recibirá los mensajes SIP del Servidor de mediación que se asociará a este tronco. Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS). Los puertos Aplicación de sucursal con funciones de supervivencia habituales son 5081 para TCP y 5082 para TLS.

6.  En **Protocolo de transporte SIP** , haga clic en el tipo de transporte que usa el punto.
    

    > [!NOTE]
    > Por motivos de seguridad, recomendamos encarecidamente que implemente un punto para el Servidor de mediación que puede usar TLS.



7.  En el **Servidor de mediación asociado** , seleccione el grupo de servidores de Servidor de mediación que asociará al tronco raíz de este punto

8.  En el **Puerto del servidor de mediación asociado** , escriba el puerto de escucha en el que el Servidor de mediación recibirá mensajes SIP del punto.
    

    > [!NOTE]
    > Con el soporte de varios troncos en Lync Server 2013, dos troncos con nombres de tronco diferentes no se pueden configurar con el mismo <STRONG>Puerto de Servidor de mediación asociado</STRONG> y <STRONG>Puerto de escucha para la puerta de enlace IP/PSTN</STRONG>

    

    > [!NOTE]
    > Con el soporte de varios troncos en Lync Server 2013, se pueden definir varios puertos de señalización SIP en el Servidor de mediación para comunicarse con varios puntos. Cuando defina un tronco, el número del <STRONG>Puerto de Servidor de mediación asociado</STRONG> debe estar en el intervalo de los puertos de escucha para el protocolo respectivo permitido por el Servidor de mediación. Este intervalo de puerto se define en Lync Server 2013 y Grupos de servidores de mediación. Haga clic con el botón secundario en el Grupo de servidores de mediación pertinente y seleccione <STRONG>Editar propiedades</STRONG> . Especifique el intervalo de puertos en el campo <STRONG>Puertos de escucha</STRONG> .



9.  Haga clic en **Aceptar**.

## Vea también

#### Tareas

[Modificación de un tronco en el Generador de topologías en Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)

