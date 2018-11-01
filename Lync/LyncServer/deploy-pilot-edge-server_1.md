---
title: Implementar el servidor perimetral piloto
TOCTitle: Implementar el servidor perimetral piloto
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48274476
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar el servidor perimetral piloto

 

_**Última modificación del tema:** 2012-10-19_

En este tema se resaltan los valores de configuración que debe tener en cuenta antes de implementar su Lync Server 2013  Servidor perimetral. En esta sección solo se destacan los puntos clave que se deben tener en cuenta como parte de la implementación de un grupo de servidores perimetrales piloto. Para obtener pasos detallados, vea [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de los usuarios externos.

Al navegar por el asistente **Definir nuevo grupo de servidores perimetrales**, repase las principales opciones de configuración recogidas en cada paso. Observe que solo se muestran unas cuantas páginas de **Definir nuevo grupo de servidores perimetrales**este asistente.

**Definir un grupo de servidores perimetrales**

1.  Abra la topología del grupo piloto en Generador de topologías.

2.  Desplácese hasta el nodo Lync Server 2013. haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.
    
    ![Cuadro de diálogo Definir el nuevo grupo de servidores perimetrales](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Cuadro de diálogo Definir el nuevo grupo de servidores perimetrales")

3.  Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.
    
    ![Cuadro de diálogo Definir el FQDN del grupo de servidores perimetrales](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Cuadro de diálogo Definir el FQDN del grupo de servidores perimetrales")

4.  En la página **Seleccionar características**, no habilite la federación o federación XMPP. La federación y la federación XMPP actualmente se enrutan a través del Office Communications Server 2007 R2Servidor perimetral heredado. Estas características se configurarán en una fase posterior de la migración.
    
    ![Cuadro de diálogo Seleccionar características](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")

5.  Tras ello, siga cumplimentando las siguientes páginas del asistente: **Seleccionar opciones de IP**, **FQDN externos**, **Definir la dirección IP interna** y **Definir la dirección IP externa**.

6.  En la página **Definir el próximo salto**, seleccione el Director del próximo salto del Lync Server 2013 Grupo de servidores perimetrales.
    
    ![Cuadro de diálogo Definir nuevo grupo de servidores perimetral, lista del grupo Próximo salto](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Cuadro de diálogo Definir nuevo grupo de servidores perimetral, lista del grupo Próximo salto")

7.  En la página **Asociar grupos de servidores front-end**, no asocie un grupo a este Grupo de servidores perimetrales en este momento. Actualmente el tráfico de medios externos se enruta a través del Servidor perimetral de Office Communications Server 2007 R2. Definiremos esta configuración en una fase posterior de la migración.
    
    ![Cuadro de diálogo Definir nuevo grupo de servidores perimetrales](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Cuadro de diálogo Definir nuevo grupo de servidores perimetrales")

8.  Haga clic en **Finalizar** y después en **Publicar** la topología.

9.  Siga los pasos descritos en [Instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo Servidor perimetral, configurar los certificados e iniciar los servicios.

Es de suma importancia que siga las instrucciones de los temas [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) de la documentación de implementación. En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor.

Ahora debería tener una implementación de servidor perimetral de Office Communications Server 2007 R2 heredada en paralelo con una implementación de servidor perimetral de Lync Server 2013. La federación está configurada para usar el Director de Office Communications Server 2007 R2. Compruebe que ambas implementaciones se ejecutan correctamente, y que puede administrar cada implementación antes de pasar a la fase siguiente.

![Generador de topologías mostrando el servidor perimetral OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Generador de topologías mostrando el servidor perimetral OCS")

