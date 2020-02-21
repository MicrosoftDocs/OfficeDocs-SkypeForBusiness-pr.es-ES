---
title: 'Lync Server 2013: flujos de llamadas de respuesta de voz interactivas de diseño'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78032a23fce6bb210ecec6eb828178aabddf9b52
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a>Diseñar flujos de llamadas de respuesta de voz interactiva en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

La respuesta interactiva de voz (IVR) se usa para obtener información de los autores de las llamadas y remitirlos a la cola correspondiente. Puede especificar pares de pregunta y respuesta, y usarlos para la navegación de llamadas. Dependiendo de la respuesta del autor de la llamada, este oye una pregunta de seguimiento o se enruta a la cola adecuada. Las preguntas de IVR y las respuestas del autor de la llamada se proporcionan al agente encargado de responder cuando este acepta la llamada. Este sistema proporciona una valiosa información al agente encargado de responder.

<div>

## <a name="overview-of-ivr-features"></a>Información general de las características de IVR

La aplicación de grupo de respuesta ofrece capacidades de reconocimiento de voz y de texto a voz en 26 idiomas. Puede formular preguntas al IVR mediante texto a voz o un archivo wave (.wave) o Windows Media Audio (.wma). Los autores de las llamadas pueden responder mediante voz o tono de marcado de frecuencia múltiple (DTMF).

Los flujos de trabajo interactivos admiten hasta dos niveles de preguntas; cada una de las preguntas tiene dos respuestas posibles. El IVR plantea al autor de la llamada una pregunta con un máximo de cuatro respuestas posibles y, según la respuesta del autor de la llamada, lo enruta a una cola o plantea otra pregunta. La segunda pregunta también puede tener cuatro respuestas posibles. Según la respuesta a la pregunta de segundo nivel, el autor de la llamada se enruta a la cola adecuada.

<div>


> [!NOTE]  
> Al diseñar flujos de llamadas mediante el shell de administración de Lync Server, puede definir cualquier cantidad de niveles de preguntas de IVR y cualquier número de respuestas. Sin embargo, para mejorar la usabilidad, le recomendamos que no use más de tres niveles de preguntas, con no más de cinco respuestas por pregunta. Además, si diseña un flujo de llamadas que tiene más de dos niveles de preguntas con más de cuatro respuestas cada una, no puede editar el flujo de llamadas mediante el panel de control de Lync Server 2013.



</div>

Las preguntas de IVR y las respuestas del autor de la llamada se proporcionan al agente encargado de responder cuando este acepta la llamada.

</div>

<div>

## <a name="working-with-speech-technologies"></a>Trabajar con tecnologías de voz

Las tecnologías de voz, como el reconocimiento de voz y el texto a voz, pueden mejorar la experiencia del cliente y permitir que las personas tengan acceso a la información con mayor naturalidad y eficacia. Sin embargo, puede haber casos en que el motor de síntesis de voz no reconozca correctamente el texto especificado o la respuesta de voz del usuario. Por ejemplo, el motor\#de texto a voz traduce el símbolo "" como la palabra "número". Este problema se puede mitigar de la siguiente manera:

  - El motor de síntesis de voz proporciona el autor de la llamada cinco intentos para responder a la pregunta. Si el autor de la llamada aporta una respuesta incorrecta (es decir, la respuesta no es ninguna de las especificadas), o si no responde, tendrá otra oportunidad para responder. El autor de la llamada tendrá cinco intentos para responder a la pregunta antes de ser desconectado. Puede configurar el IVR para que reproduzca un mensaje personalizado después de cada error del autor de la llamada. La pregunta se repite cada vez.

  - Para reducir al máximo la posibilidad de que el motor de voz interprete el ruido ambiental como una respuesta, use respuestas más largas. Por ejemplo, cada respuesta debe tener más de una sílaba y debe sonar de forma significativamente distinta a las demás.

  - Si sus preguntas tienen respuestas de voz y de DTMF, configure las respuestas de voz con palabras que representen el concepto, en lugar de la respuesta de DTMF. Por ejemplo, en lugar de "Pulse o diga uno", use "Pulse 1 o diga facturación".

  - Después de diseñar IVR, llame al flujo de trabajo, escuche las indicaciones, responda a cada una de ellas mediante voz y compruebe que IVR suena y se comporta como se espera. A continuación, puede modificar el IVR para corregir los posibles problemas de interpretación. Siguiendo el ejemplo anterior, si necesita hacer referencia a la \# clave, puede volver a escribir el mensaje IVR para usar el nombre de la clave, en lugar \# del símbolo. Por ejemplo, "Para hablar con el departamento de ventas, presione la tecla almohadilla".

</div>

<div>

## <a name="ivr-design-examples"></a>Ejemplos de diseño de IVR

Los siguientes apartados contienen ejemplos de escenarios de IVR y pares de preguntas y respuestas.

<div>

## <a name="ivr-with-one-level-of-questions"></a>IVR con preguntas de un nivel

En el ejemplo siguiente se muestra un IVR con un nivel de preguntas. En él se usa el reconocimiento de voz para detectar la respuesta del autor de la llamada.

**Pregunta:** "Gracias por llamar a Recursos Humanos. Si desea hablar con Nóminas, diga nóminas. Si no, diga recursos humanos".

  - **Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de nóminas.

  - **Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de recursos humanos.

En la figura siguiente se muestra el flujo de la llamada.

**Flujo de llamada interactiva de un nivel**

![Diseñar flujos de llamadas mediante la función de voz interactiva](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Diseñar flujos de llamadas mediante la función de voz interactiva")

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a>IVR con dos niveles de preguntas

En el ejemplo siguiente, se muestra un IVR con dos niveles de preguntas. Permite a los autores de las llamadas responder mediante voz o el teclado numérico DTMF.

**Pregunta:** "Gracias por llamar al Centro de Asistencia Técnica. Si tiene un problema de acceso a la red, pulse o diga 1. Si tiene un problema de software, pulse o diga 2. Si tiene un problema de hardware, pulse o diga 3".

  - **Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de red.

  - **Se ha seleccionado la opción 2:** Se hace una pregunta de seguimiento al autor de la llamada:
    
    **Pregunta:** "Si se trata de un problema con el sistema operativo, pulse o diga 1. Si se trata de un problema con una aplicación interna, pulse o diga 2. Si no se trata de ninguna de estas opciones, pulse o diga 3".
    
      - **Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de sistemas operativos.
    
      - **Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de asistencia de aplicaciones internas.
    
      - **Se ha seleccionado la opción 3:** el autor de la llamada se enruta al equipo de asistencia de software.

  - **Se ha seleccionado la opción 3:** Se hace una pregunta de seguimiento al autor de la llamada:
    
    **Pregunta:** "Si se trata de un problema con la impresora, pulse 1. En caso contrario, pulse 2".
    
      - **Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de impresoras.
    
      - **Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de asistencia de hardware.

En la figura siguiente se muestra el flujo de la llamada.

**Flujo de llamada interactiva de dos niveles**

![Diseñar flujos de llamadas mediante la función de voz interactiva](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Diseñar flujos de llamadas mediante la función de voz interactiva")

</div>

</div>

<div>

## <a name="best-practices"></a>Recomendaciones

En la lista siguiente se describen algunas técnicas recomendadas para diseñar IVR:

  - Permita el autor de la llamada llegar rápidamente a la tarea. Evite el exceso de información o mensajes de marketing largos en el IVR.

  - Si desea incluir un mensaje largo, puede añadirlo a la primera pregunta, en lugar del mensaje de bienvenida. Los autores de las llamadas pueden omitir el mensaje si forma parte de la primera pregunta, respondiéndola, pero no pueden omitir el mensaje de bienvenida.

  - Hable en el idioma del autor de la llamada. Evite usar un lenguaje rebuscado. Hable con naturalidad.

  - Escriba indicaciones efectivas. Quite todas las opciones innecesarias. Estructure la información de forma que la respuesta esperada del autor de la llamada esté al final de la frase. Por ejemplo, "Para hablar con el equipo de ventas, pulse 1".

  - Haga que las respuestas de voz sean fáciles para el usuario. Por ejemplo, si incluye respuestas de DTMF y de voz, use algo así: "Para hablar con el equipo de ventas, pulse 1 o diga ventas".

  - Pruebe el IVR con un grupo de usuarios antes de implementarlo en toda la organización.

</div>

</div>

<span> </span>

</div>

</div>

</div>

