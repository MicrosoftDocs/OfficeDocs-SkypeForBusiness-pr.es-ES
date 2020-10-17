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
ms.openlocfilehash: 649d085253610002e7623872012a400ac0a1f079
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498947"
---
# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="3c128-102">Diseñar flujos de llamadas de respuesta de voz interactiva en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c128-102">Design interactive voice response call flows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c128-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="3c128-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="3c128-p101">La respuesta interactiva de voz (IVR) se usa para obtener información de los autores de las llamadas y remitirlos a la cola correspondiente. Puede especificar pares de pregunta y respuesta, y usarlos para la navegación de llamadas. Dependiendo de la respuesta del autor de la llamada, este oye una pregunta de seguimiento o se enruta a la cola adecuada. Las preguntas de IVR y las respuestas del autor de la llamada se proporcionan al agente encargado de responder cuando este acepta la llamada. Este sistema proporciona una valiosa información al agente encargado de responder.</span><span class="sxs-lookup"><span data-stu-id="3c128-p101">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue. Question-and-answer pairs determine which queue to use. Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue. The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="3c128-108">Información general de las características de IVR</span><span class="sxs-lookup"><span data-stu-id="3c128-108">Overview of IVR Features</span></span>

<span data-ttu-id="3c128-109">La aplicación de grupo de respuesta ofrece capacidades de reconocimiento de voz y de texto a voz en 26 idiomas.</span><span class="sxs-lookup"><span data-stu-id="3c128-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="3c128-110">Puede formular preguntas al IVR mediante texto a voz o un archivo wave (.wave) o Windows Media Audio (.wma).</span><span class="sxs-lookup"><span data-stu-id="3c128-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="3c128-111">Los autores de las llamadas pueden responder mediante voz o tono de marcado de frecuencia múltiple (DTMF).</span><span class="sxs-lookup"><span data-stu-id="3c128-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="3c128-p103">Los flujos de trabajo interactivos admiten hasta dos niveles de preguntas; cada una de las preguntas tiene dos respuestas posibles. El IVR plantea al autor de la llamada una pregunta con un máximo de cuatro respuestas posibles y, según la respuesta del autor de la llamada, lo enruta a una cola o plantea otra pregunta. La segunda pregunta también puede tener cuatro respuestas posibles. Según la respuesta a la pregunta de segundo nivel, el autor de la llamada se enruta a la cola adecuada.</span><span class="sxs-lookup"><span data-stu-id="3c128-p103">Interactive workflows support up to two levels of questions, with each question having up to four possible answers. The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question. The second question can also have four possible answers. Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c128-116">Al diseñar flujos de llamadas mediante el shell de administración de Lync Server, puede definir cualquier cantidad de niveles de preguntas de IVR y cualquier número de respuestas.</span><span class="sxs-lookup"><span data-stu-id="3c128-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="3c128-117">Sin embargo, para mejorar la usabilidad, le recomendamos que no use más de tres niveles de preguntas, con no más de cinco respuestas por pregunta.</span><span class="sxs-lookup"><span data-stu-id="3c128-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="3c128-118">Además, si diseña un flujo de llamadas que tiene más de dos niveles de preguntas con más de cuatro respuestas cada una, no puede editar el flujo de llamadas mediante el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c128-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="3c128-119">Las preguntas de IVR y las respuestas del autor de la llamada se proporcionan al agente encargado de responder cuando este acepta la llamada.</span><span class="sxs-lookup"><span data-stu-id="3c128-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="3c128-120">Trabajar con tecnologías de voz</span><span class="sxs-lookup"><span data-stu-id="3c128-120">Working with Speech Technologies</span></span>

<span data-ttu-id="3c128-121">Las tecnologías de voz, como el reconocimiento de voz y el texto a voz, pueden mejorar la experiencia del cliente y permitir que las personas tengan acceso a la información con mayor naturalidad y eficacia.</span><span class="sxs-lookup"><span data-stu-id="3c128-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="3c128-122">Sin embargo, puede haber casos en que el motor de síntesis de voz no reconozca correctamente el texto especificado o la respuesta de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="3c128-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="3c128-123">Por ejemplo, el \# motor de texto a voz traduce el símbolo "" como la palabra "número".</span><span class="sxs-lookup"><span data-stu-id="3c128-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="3c128-124">Este problema se puede mitigar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3c128-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="3c128-p106">El motor de síntesis de voz proporciona el autor de la llamada cinco intentos para responder a la pregunta. Si el autor de la llamada aporta una respuesta incorrecta (es decir, la respuesta no es ninguna de las especificadas), o si no responde, tendrá otra oportunidad para responder. El autor de la llamada tendrá cinco intentos para responder a la pregunta antes de ser desconectado. Puede configurar el IVR para que reproduzca un mensaje personalizado después de cada error del autor de la llamada. La pregunta se repite cada vez.</span><span class="sxs-lookup"><span data-stu-id="3c128-p106">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

  - <span data-ttu-id="3c128-p107">Para reducir al máximo la posibilidad de que el motor de voz interprete el ruido ambiental como una respuesta, use respuestas más largas. Por ejemplo, cada respuesta debe tener más de una sílaba y debe sonar de forma significativamente distinta a las demás.</span><span class="sxs-lookup"><span data-stu-id="3c128-p107">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="3c128-p108">Si sus preguntas tienen respuestas de voz y de DTMF, configure las respuestas de voz con palabras que representen el concepto, en lugar de la respuesta de DTMF. Por ejemplo, en lugar de "Pulse o diga uno", use "Pulse 1 o diga facturación".</span><span class="sxs-lookup"><span data-stu-id="3c128-p108">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="3c128-134">Después de diseñar IVR, llame al flujo de trabajo, escuche las indicaciones, responda a cada una de ellas mediante voz y compruebe que IVR suena y se comporta como se espera.</span><span class="sxs-lookup"><span data-stu-id="3c128-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="3c128-135">A continuación, puede modificar el IVR para corregir los posibles problemas de interpretación.</span><span class="sxs-lookup"><span data-stu-id="3c128-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="3c128-136">Siguiendo el ejemplo anterior, si necesita hacer referencia a la \# clave, puede volver a escribir el mensaje IVR para usar el nombre de la clave, en lugar del \# símbolo.</span><span class="sxs-lookup"><span data-stu-id="3c128-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="3c128-137">Por ejemplo, "Para hablar con el departamento de ventas, presione la tecla almohadilla".</span><span class="sxs-lookup"><span data-stu-id="3c128-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="3c128-138">Ejemplos de diseño de IVR</span><span class="sxs-lookup"><span data-stu-id="3c128-138">IVR Design Examples</span></span>

<span data-ttu-id="3c128-139">Los siguientes apartados contienen ejemplos de escenarios de IVR y pares de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="3c128-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="3c128-140">IVR con preguntas de un nivel</span><span class="sxs-lookup"><span data-stu-id="3c128-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="3c128-p110">En el ejemplo siguiente se muestra un IVR con un nivel de preguntas. En él se usa el reconocimiento de voz para detectar la respuesta del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3c128-p110">The following example shows an IVR that uses one level of questions. It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="3c128-p111">**Pregunta:** "Gracias por llamar a Recursos Humanos. Si desea hablar con Nóminas, diga nóminas. Si no, diga recursos humanos".</span><span class="sxs-lookup"><span data-stu-id="3c128-p111">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

  - <span data-ttu-id="3c128-146">**Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de nóminas.</span><span class="sxs-lookup"><span data-stu-id="3c128-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="3c128-147">**Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="3c128-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="3c128-148">En la figura siguiente se muestra el flujo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3c128-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="3c128-149">**Flujo de llamada interactiva de un nivel**</span><span class="sxs-lookup"><span data-stu-id="3c128-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="3c128-150">![Diseñar flujos de llamadas mediante la función de voz interactiva](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Diseñar flujos de llamadas mediante la función de voz interactiva")</span><span class="sxs-lookup"><span data-stu-id="3c128-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="3c128-151">IVR con dos niveles de preguntas</span><span class="sxs-lookup"><span data-stu-id="3c128-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="3c128-p112">En el ejemplo siguiente, se muestra un IVR con dos niveles de preguntas. Permite a los autores de las llamadas responder mediante voz o el teclado numérico DTMF.</span><span class="sxs-lookup"><span data-stu-id="3c128-p112">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="3c128-p113">**Pregunta:** "Gracias por llamar al Centro de Asistencia Técnica. Si tiene un problema de acceso a la red, pulse o diga 1. Si tiene un problema de software, pulse o diga 2. Si tiene un problema de hardware, pulse o diga 3".</span><span class="sxs-lookup"><span data-stu-id="3c128-p113">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="3c128-158">**Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de red.</span><span class="sxs-lookup"><span data-stu-id="3c128-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="3c128-159">**Se ha seleccionado la opción 2:** Se hace una pregunta de seguimiento al autor de la llamada:</span><span class="sxs-lookup"><span data-stu-id="3c128-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="3c128-p114">**Pregunta:** "Si se trata de un problema con el sistema operativo, pulse o diga 1. Si se trata de un problema con una aplicación interna, pulse o diga 2. Si no se trata de ninguna de estas opciones, pulse o diga 3".</span><span class="sxs-lookup"><span data-stu-id="3c128-p114">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="3c128-163">**Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="3c128-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="3c128-164">**Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de asistencia de aplicaciones internas.</span><span class="sxs-lookup"><span data-stu-id="3c128-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="3c128-165">**Se ha seleccionado la opción 3:** el autor de la llamada se enruta al equipo de asistencia de software.</span><span class="sxs-lookup"><span data-stu-id="3c128-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="3c128-166">**Se ha seleccionado la opción 3:** Se hace una pregunta de seguimiento al autor de la llamada:</span><span class="sxs-lookup"><span data-stu-id="3c128-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="3c128-p115">**Pregunta:** "Si se trata de un problema con la impresora, pulse 1. En caso contrario, pulse 2".</span><span class="sxs-lookup"><span data-stu-id="3c128-p115">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="3c128-169">**Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de impresoras.</span><span class="sxs-lookup"><span data-stu-id="3c128-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="3c128-170">**Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de asistencia de hardware.</span><span class="sxs-lookup"><span data-stu-id="3c128-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="3c128-171">En la figura siguiente se muestra el flujo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3c128-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="3c128-172">**Flujo de llamada interactiva de dos niveles**</span><span class="sxs-lookup"><span data-stu-id="3c128-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="3c128-173">![Diseñar flujos de llamadas mediante la función de voz interactiva](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Diseñar flujos de llamadas mediante la función de voz interactiva")</span><span class="sxs-lookup"><span data-stu-id="3c128-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="3c128-174">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="3c128-174">Best Practices</span></span>

<span data-ttu-id="3c128-175">En la lista siguiente se describen algunas técnicas recomendadas para diseñar IVR:</span><span class="sxs-lookup"><span data-stu-id="3c128-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="3c128-p116">Permita el autor de la llamada llegar rápidamente a la tarea. Evite el exceso de información o mensajes de marketing largos en el IVR.</span><span class="sxs-lookup"><span data-stu-id="3c128-p116">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="3c128-p117">Si desea incluir un mensaje largo, puede añadirlo a la primera pregunta, en lugar del mensaje de bienvenida. Los autores de las llamadas pueden omitir el mensaje si forma parte de la primera pregunta, respondiéndola, pero no pueden omitir el mensaje de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="3c128-p117">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="3c128-p118">Hable en el idioma del autor de la llamada. Evite usar un lenguaje rebuscado. Hable con naturalidad.</span><span class="sxs-lookup"><span data-stu-id="3c128-p118">Speak in the caller’s language. Avoid stilted language. Speak naturally.</span></span>

  - <span data-ttu-id="3c128-p119">Escriba indicaciones efectivas. Quite todas las opciones innecesarias. Estructure la información de forma que la respuesta esperada del autor de la llamada esté al final de la frase. Por ejemplo, "Para hablar con el equipo de ventas, pulse 1".</span><span class="sxs-lookup"><span data-stu-id="3c128-p119">Write efficient and effective prompts. Remove any unnecessary options. Structure the information so that the caller’s expected response is at the end of the sentence. For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="3c128-p120">Haga que las respuestas de voz sean fáciles para el usuario. Por ejemplo, si incluye respuestas de DTMF y de voz, use algo así: "Para hablar con el equipo de ventas, pulse 1 o diga ventas".</span><span class="sxs-lookup"><span data-stu-id="3c128-p120">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="3c128-189">Pruebe el IVR con un grupo de usuarios antes de implementarlo en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="3c128-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

