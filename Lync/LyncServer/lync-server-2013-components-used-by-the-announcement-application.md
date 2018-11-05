---
title: 'Lync Server 2013: Componentes que usa la aplicación Anuncio'
TOCTitle: Componentes que usa la aplicación Anuncio
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48275768
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes que usa la aplicación Anuncio en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-13_

En Lync Server 2013, la Aplicación de anuncio es un componente de la Aplicación de grupo de respuesta. Al implementar Telefonía IP empresarial, la Aplicación de anuncio se instala y se activa automáticamente junto con la Aplicación de grupo de respuesta. En esta sección se describen los componentes compatibles con la Aplicación de anuncio.

## Componentes de la aplicación de anuncio

Los siguientes componentes de Lync Server son compatibles con la Aplicación de anuncio:

  - **Servicio de aplicaciones**    Servicio de aplicaciones proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas. Servicio de aplicaciones se instala automáticamente en cada servidor front-end, en un Grupo de servidores front-end, y en cada servidor Standard Edition.

  - **Aplicación de grupo de respuesta**   La Aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que el Servicio de aplicaciones hospeda. Cuando hay un intervalo de números de teléfono sin asignar configurado para enrutar a un anuncio, se necesita que la Aplicación de grupo de respuesta enrute las llamadas realizadas a ese número de teléfono. ( Aplicación de grupo de respuesta no es necesario si todos los intervalos se han configurado para enrutar a la mensajería unificada (UM) de Exchange).

  - **Archivos de audio**   Los archivos de audio se usan para los anuncios.

  - **Almacén de archivos**   La Aplicación de anuncio usa el almacén de archivos para almacenar sus archivos de audio.

  - **Panel de control de Lync Server**   Puede usar Panel de control de Lync Server para configurar la tabla de números sin asignar.

  - **Shell de administración de Lync Server**   Puede usar los cmdlets del Shell de administración de Lync Server para configurar los anuncios y la tabla de números sin asignar.

