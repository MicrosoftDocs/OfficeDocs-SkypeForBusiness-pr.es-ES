---
title: 'Lync Server 2013: Componentes usados por el grupo de respuesta'
TOCTitle: Componentes usados por el grupo de respuesta
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48274761
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes usados por el grupo de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-11_

La Aplicación de grupo de respuesta se habilita automáticamente al implementar Telefonía IP empresarial. En esta sección se describen los componentes compatibles con la Aplicación de grupo de respuesta.

## Componentes del grupo de respuesta

Los siguientes componentes de Microsoft Lync Server 2013 son compatibles con la Aplicación de grupo de respuesta:

  - **Servicio de aplicaciones**   El Servicio de aplicaciones incorpora una plataforma para implementar, hospedar y administrar las aplicaciones de comunicaciones unificadas, como, por ejemplo, el Grupo de respuesta. El Servicio de aplicaciones se instala automáticamente en todos los servidores front-end de un Grupo de servidores front-end, así como en cada servidor Standard Edition.

  - **Aplicación de grupo de respuesta**   La Aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que el Servicio de aplicaciones hospeda. Se incluye automáticamente al implementar Grupo de respuesta. La Aplicación de grupo de respuesta enruta y pone en cola las llamadas entrantes a los grupos de agentes.

  - **Paquete de idioma**   Se necesita un paquete de idioma para admitir las tecnologías de texto a voz y reconocimiento de voz, que se usan cuando se configuran mensajes (como el mensaje de bienvenida o cualquier otro) y preguntas y respuestas de respuesta interactiva de voz (IVR). De forma predeterminada, los 26 paquetes de idioma posibles se instalan cuando Lync Server 2013 se implementa.

  - **Archivos de audio**   Los archivos de audio se usan para los mensajes y la música en espera.

  - **Almacén de archivos**   El Grupo de respuesta emplea el almacén de archivos para almacenar los archivos de audio. Distintos grupos de Grupo de respuesta pueden usar la misma instancia del almacén de archivos.

  - **Herramienta de configuración de grupo de respuesta**   La Herramienta de configuración de grupo de respuesta es una herramienta basada en web que sirve para crear y configurar grupos de respuesta. La Herramienta de configuración de grupo de respuesta se incluye al instalar los servicios web.

  - **Panel de control de Microsoft Lync Server 2013**   El Panel de control de Lync Server se puede usar para instalar y configurar grupos de agentes y colas para los grupos de respuesta.

  - **Shell de administración de Lync Server**   Toda la configuración de Grupo de respuesta se puede definir por medio de los cmdlet del Shell de administración de Lync Server.

  - **Microsoft Lync 2013**   Los agentes formales (los agentes que han de iniciar sesión en el grupo para que se puedan aceptar llamadas para el grupo) usan Lync 2013 para iniciar y cerrar sesión en el grupo. Si hay un grupo de agentes configurado para los agentes formales, los agentes hacen clic en un elemento de menú en Lync 2013 para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.

  - **Servicios web**   Los servicios web son necesarios para la Herramienta de configuración de grupo de respuesta, la consola de inicio y cierre de sesión de los agentes, el Panel de control de Lync Server y el servicio web de cliente del Grupo de respuesta.

  - **Servicio web de cliente de grupo de respuesta**   La Aplicación de grupo de respuesta ofrece un servicio web de cliente que las aplicaciones de otros fabricantes pueden usar para obtener información sobre los clientes, la pertenencia de un grupo de agentes, el estado de inicio de sesión de los agentes, el estado de llamada de los grupos y los grupos que admiten llamadas anónimas. Lync 2013 y Operador de Lync 2010 usan el servicio web de cliente de Grupo de respuesta para hacerse con la lista de grupos de respuesta que los agentes pueden usar para realizar llamadas anónimas. El servicio web de cliente se incluye al instalar los servicios web.

