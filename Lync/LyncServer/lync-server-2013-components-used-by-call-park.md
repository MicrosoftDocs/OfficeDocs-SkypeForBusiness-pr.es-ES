---
title: 'Lync Server 2013: Componentes que usa el estacionamiento de llamadas'
TOCTitle: Componentes que usa el estacionamiento de llamadas
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48276641
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes que usa el estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-13_

La Aplicación de estacionamiento de llamadas se instala automáticamente cuando implementa la Telefonía IP empresarial. Permite el Estacionamiento de llamadas configurando la directiva de voz. Los siguientes componentes de Lync Server 2013 son compatibles con la Aplicación de estacionamiento de llamadas:

  - **Servicio de aplicaciones**   El Servicio de aplicaciones proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como la Aplicación de estacionamiento de llamadas. El Servicio de aplicaciones se instala automáticamente en cada servidor front-end en un Grupo de servidores front-end y en cada servidor Standard Edition.

  - **Aplicación de estacionamiento de llamadas**   La Aplicación de estacionamiento de llamadas es una de las aplicaciones de comunicaciones unificadas que el Servicio de aplicaciones hospeda. Se incluye automáticamente al implementar la Telefonía IP empresarial. El Estacionamiento de llamadas estaciona y recupera llamadas y administra órbitas del Estacionamiento de llamadas.

  - **Archivo de música en espera**   Si la música está habilitada, el archivo de música se reproduce mientras se estaciona una llamada. Se incluye un archivo de música predeterminado al instalar la Aplicación de estacionamiento de llamadas.

  - **Almacén de archivos**   La Aplicación de estacionamiento de llamadas usa el almacén de archivos para conservar archivos de audio personalizados.

  - **Panel de control de Lync Server**   Puede usar el Panel de control de Lync Server para configurar la tabla de órbitas del Estacionamiento de llamadas y para habilitar el Estacionamiento de llamadas para los usuarios.

  - **Shell de administración de Lync Server**   Toda la configuración de la Aplicación de estacionamiento de llamadas se puede realizar mediante los cmdlets del Shell de administración de Lync Server.

