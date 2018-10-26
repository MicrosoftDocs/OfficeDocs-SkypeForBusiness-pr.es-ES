---
title: Implementar un servidor perimetral piloto
TOCTitle: Implementar un servidor perimetral piloto
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48276877
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar un servidor perimetral piloto

 

_**Última modificación del tema:** 2012-10-19_

En esta sección se destacan las configuraciones que debe tener en cuenta antes de implementar Lync Server 2013 Servidor perimetral. Los procesos de implementación y configuración de Lync Server 2013 son muy parecidos a Lync Server 2010. En esta sección solo se destacan los puntos clave que se deben tener en cuenta como parte de la implementación de un grupo piloto. Para informarse detalladamente, vea [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación, en la que se describe el proceso de implementación y, asimismo, se ofrece información de configuración para el acceso de los usuarios externos.

Al navegar por el asistente **Definir nuevo grupo de servidores perimetrales**, repase las principales opciones de configuración recogidas en cada paso. Observe que solo se muestran unas cuantas páginas de este asistente.

**Definir un grupo de servidores perimetrales**

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Desplácese hasta el nodo Lync Server 2013. haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.
    
    ![Cuadro de diálogo Definir el nuevo grupo de servidores perimetrales](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Cuadro de diálogo Definir el nuevo grupo de servidores perimetrales")

3.  Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.
    
    ![Cuadro de diálogo Definir el FQDN del grupo de servidores perimetrales](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Cuadro de diálogo Definir el FQDN del grupo de servidores perimetrales")

4.  En la página **Seleccionar características**, no habilite la federación ni la federación XMPP. La federación y la federación XMPP actualmente se redirigen a través del Servidor perimetral de Lync Server 2010heredado. Estas características se configurarán en una fase posterior de la migración.
    
    ![Cuadro de diálogo Seleccionar características](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")

5.  Tras ello, siga cumplimentando las siguientes páginas del asistente: **FQDN externos**, **Definir la dirección IP interna** y **Definir la dirección IP externa**.

6.  En la página **Definir el próximo salto**, seleccione el Director para el próximo salto del Grupo de servidores perimetrales de Lync Server 2010.
    
    ![Cuadro de diálogo Definir el próximo salto](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Cuadro de diálogo Definir el próximo salto")

7.  En la página **Asociar grupos de servidores de mediación o front-end**, no asocie un grupo de servidores a este Grupo de servidores perimetrales en este momento. Actualmente el tráfico de medios externos se redirige a través del Lync Server 2010 de Servidor perimetral. Definiremos esta configuración en una fase posterior de la migración.
    
    ![Cuadro de diálogo Asociar grupos de servidores front-end](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Cuadro de diálogo Asociar grupos de servidores front-end")

8.  Haga clic en **Finalizar** y después en **Publicar** la topología.

9.  Siga los pasos descritos en [Instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo Servidor perimetral, configurar los certificados e iniciar los servicios.

Es de suma importancia que siga las instrucciones de los temas [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) de la documentación de implementación. En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor.

Ahora tiene un servidor perimetral de Lync Server 2010heredado, implementado en paralelo con una implementación de servidor perimetral Lync Server 2013. Compruebe que las dos implementaciones se ejecuten correctamente, se inician los servicios y puede administrar cada implementación anterior para pasar a la fase siguiente.

