---
title: Comprobar el entorno de Lync Server 2010
TOCTitle: Comprobar el entorno de Lync Server 2010
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48276557
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar el entorno de Lync Server 2010

 

_**Última modificación del tema:** 2012-10-19_

Antes de implementar Lync Server 2013 para que coexista con Lync Server 2010, debe comprobar que los servicios de Lync Server 2010 se han configurado e iniciado. Es importante identificar los servicios y las características clave que existen en el entorno heredado antes de implementar un grupo piloto de Lync Server 2013. Antes de implementar XMPP de Microsoft Lync Server 2013 para que coexista con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredados se han configurado e iniciado, e identificar al socio federado compatible con la configuración de XMPP heredada. La comprobación de la implementación de Lync Server 2010 heredada conlleva:

  - Comprobar que los servicios de Lync Server 2010 se han iniciado.

  - Revisar la topología y los usuarios de Lync Server 2010.

  - Comprobar la configuración de la federación y del servidor perimetral.

  - Comprobar los servicios de XMPP y los socios federados.

**Comprobar que los servicios de Lync Server 2010 se han iniciado**

1.  En el servidor front-end de Lync Server 2010, desplácese hasta Herramientas administrativas\\Applet Servicios.

2.  Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:
    
    ![Lista de servicios que se ejecutan en el servidor front end](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Lista de servicios que se ejecutan en el servidor front end")

**Revisar la topología de Lync Server 2010 en Panel de control de Lync Server**

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abra el Panel de control de Lync Server.

3.  Seleccione **Topología** . Compruebe que los diversos servidores de la implementación de Lync Server 2010 aparecen enumerados.
    
    ![Página Topología del panel de control de Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Página Topología del panel de control de Lync Server 2010")

**Para revisar los usuarios de Lync Server 2010 en Panel de control de Lync Server:**

1.  Abra el Panel de control de Lync Server.

2.  Seleccione **Usuarios** y haga clic en **Buscar** .

3.  Compruebe que la columna **Grupo de registradores** apunta al grupo de Lync Server 2010 para cada usuario enumerado.
    
    ![Panel de control de Lync Server 2010 con listado de usuarios](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Panel de control de Lync Server 2010 con listado de usuarios")

**Para comprobar la configuración perimetral y de federación de Lync Server 2010:**

1.  Inicie el Generador de topologías.

2.  Seleccione **Descargar topología de la implementación existente**.

3.  Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml como valor predeterminado.

4.  Expanda el nodo de Lync Server 2010 para mostrar los diversos roles de servidor de la implementación.

5.  Seleccione el nodo del sitio y compruebe si se ha establecido un valor de **Asignación de ruta de federación del sitio**.
    
    ![Generador de topologías, ruta de federación de sitios](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generador de topologías, ruta de federación de sitios")

6.  A continuación, seleccione el grupo de servidores front-end de Standard Edition o Enterprise Edition. Determine si se ha configurado un grupo de servidores perimetrales para los medios bajo **Asociaciones**.
    
    ![Servidores y grupos de servidores en el Generador de topologías](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Servidores y grupos de servidores en el Generador de topologías")

7.  Por último, seleccione el grupo de servidores perimetrales e identifique si un grupo de próximo salto se ha configurado bajo **Selección de próximo salto**.
    
    ![Generador de topologías, selección de próximo salto](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generador de topologías, selección de próximo salto")

**Compruebe la configuración del socio federado XMPP heredado**

1.  Desde el servidor XMPP heredado, desplácese al appletAdministrative Tools\\Services.

2.  Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server.
    
    ![Servicio de puerta de enlace XMPP para Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP para Office Communications Server")

