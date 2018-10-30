---
title: "Lync Server 2013 : Act. d’une stratégie de serveur de conversation permanente"
TOCTitle: Habilitar la directiva de servidor de chat persistente
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48275914
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar la directiva de servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

En el Panel de control de Lync Server 2013, puede usar la página **Directiva de Chat persistente** del grupo **Chat persistente** para administrar directivas de nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o más directivas de usuario y de sitio adicionales para su implementación. Si la directiva habilitó a un usuario para Servidor de chat persistente, el entorno Servidor de chat persistente aparecerá en su cliente Lync 2013


> [!NOTE]
> En la topología, las directivas de sitio de Servidor de chat persistente se aplican globalmente según el grupo del usuario o el sitio del usuario o el usuario.



La directiva global se crea automáticamente cuando se implementa un Servidor de chat persistente y puede configurarse, pero no eliminarse. Debido a que la política global se aplica a todos los usuarios, no debe configurarse para cada usuario.

Puede crear y configurar las directivas de usuario y múltiples sitios que junto con directiva global habilitan a los usuarios para Servidor de chat persistente. Las directivas de Servidor de chat persistente de sitio y de grupo anulan la directiva global de Servidor de chat persistente, pero solo para los usuarios de ese sitio. Las directivas de usuario anulan las directivas globales, de grupo y de sitio para los usuarios a los que se asigna la directiva de usuario.


> [!NOTE]
> Para configurar y usar el Servidor de chat persistente, primero debe usar el Generador de topologías a fin de agregar la compatibilidad del Servidor de chat persistente con la topología y, luego, publicar la topología. Para más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.



## En esta sección

  - [Configurar la directiva global para chat persistente en Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Crear una directiva de sitio para chat persistente en Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Crear una directiva de usuario para chat persistente en Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Aplicar una directiva de chat persistente a un usuario o grupo de usuarios en Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

