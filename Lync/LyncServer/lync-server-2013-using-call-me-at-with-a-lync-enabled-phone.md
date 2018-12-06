---
title: "Ut. de la fonctionnalité Appelle-moi à avec un tél. prenant en charge Lync"
TOCTitle: "Ut. de la fonctionnalité Appelle-moi à avec un tél. prenant en charge Lync"
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56559136
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar Llamarme al con un teléfono habilitado para Lync y Lync Server 2013

 

_**Última modificación del tema:** 2013-08-09_

La característica Llamarme al Lync permite a los usuarios unirse al audio de una conferencia a través de un teléfono móvil o de línea, o bien con otro dispositivo conectado a la Red telefónica conmutada (RTC). Cuando trate de unirse a una reunión con Lync, se abrirá el cuadro de diálogo **Unirse al audio de la reunión**:

![Captura de pantalla de la ventana para usar Lync para unirse a una reunión de audio](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Captura de pantalla de la ventana para usar Lync para unirse a una reunión de audio")

Si selecciona **Llamarme al**, podrá elegir un número de teléfono de la lista desplegable. Lync Server 2013 realizará una llamada al número seleccionado, lo que le permitirá usar ese teléfono para participar del audio de la conferencia.

La lista desplegable se rellena con los números de teléfono (móvil, particular u otros) que especificó en la pestaña **Teléfonos** del cuadro de diálogo **Opciones de Lync**:

![Captura de pantalla de las opciones de configuración de teléfonos en Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Captura de pantalla de las opciones de configuración de teléfonos en Lync")

Si no especificó ningún número en la pestaña **Teléfonos**, no habrá ninguno disponible en el cuadro desplegable. Pero podrá hacer clic en **Nuevo número** para que Lync Server llame al número de teléfono que quiera:

![Captura de pantalla de la ventana Llamarme para unirse a una reunión de audio en Lync](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Captura de pantalla de la ventana Llamarme para unirse a una reunión de audio en Lync")

La característica Llamarme al funciona perfectamente bien siempre que la use del modo indicado: haciendo que Lync Server llame a un número de teléfono RTC. Pero si indica a Lync Server que lo llame a un extremo habilitado para Lync (por ejemplo, un teléfono de una sala de conferencias), puede que la experiencia no sea óptima. Este es el problema que podría encontrar junto con dos modos de solucionarlo.

Para empezar, esto es lo que sucede cuando especifica un número de un teléfono habilitado para Lync en la característica Llamarme al. Suponga que Ken Myer quiere unirse a una reunión e indica a Lync Server que lo llame al 1-206-555-1219, un número de un teléfono habilitado para Lync Server. Ken podrá conectarse a la reunión, pero después de unos segundos Lync mostrará el mensaje **Llamada no completada o finalizada** y parecerá que Ken se ha desconectado de la reunión:

![Captura de pantalla de la ventana de conferencia de Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Captura de pantalla de la ventana de conferencia de Lync")

Ahora bien, observe que hay una discrepancia en la ventana de conversación de Lync. Ken Myer es el único nombre que aparece debajo del encabezado **Participantes**. Pero si observa la barra de título de la ventana, verá que la conferencia contiene un total de cuatro participantes.

Asimismo, si observa la ventana de conversación de cualquiera de los otros participantes de la conferencia, no verá a Ken Myer en ningún lado:

![Captura de pantalla de la ventana de la lista de participantes de Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Captura de pantalla de la ventana de la lista de participantes de Lync")

Aun así, Ken Myer podrá participar del audio de la llamada a través de su teléfono habilitado para Lync. La característica Llamarme al en realidad funciona, pero la experiencia no es óptima.

Hay al menos dos formas de solucionar este problema. Si ya se ha unido a una conferencia de esta manera (como lo hizo Ken Myer), puede solucionar el problema usando otra modalidad. Por ejemplo, si envía un mensaje instantáneo, la ventana de conversación mostrará a todos los participantes de la conferencia, incluso a usted:

![Captura de pantalla de la lista de conversaciones y participantes de Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Captura de pantalla de la lista de conversaciones y participantes de Lync")

En este momento, podrá participar de la reunión tal como lo espera.

O bien, puede evitar este problema por completo cambiando el modo de unirse a la reunión. Si necesita que Lync Server llame a un teléfono habilitado para Lync Server, puede unirse a la reunión sin conexión de audio. Para ello, seleccione No unirse al audio cuando aparezca el cuadro de diálogo Unirse al audio de la reunión:

![Captura de pantalla de la ventana para rechazar unirse a una reunión de audio en Lync](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Captura de pantalla de la ventana para rechazar unirse a una reunión de audio en Lync")

Una vez que se conecte a la reunión correctamente, puede “invitar” al teléfono habilitado para Lync Server a unirse también a la reunión. Para hacerlo, coloque el mouse sobre el icono Personas y haga clic en **Invitar a más personas**:

![Captura de pantalla de la ventana para invitar a más participantes en Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Captura de pantalla de la ventana para invitar a más participantes en Lync")

Se abrirá el cuadro de diálogo **Enviar un mensaje instantáneo**. No preste atención al título del cuadro (en realidad no enviará un mensaje instantáneo) y escriba el número del teléfono habilitado para Lync:

![Captura de pantalla del cuadro de diálogo Enviar un mensaje instantáneo](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Captura de pantalla del cuadro de diálogo Enviar un mensaje instantáneo")

Cuando haga clic en **Aceptar**, Lync Server llamará al número que escribió en el cuadro de diálogo. Una vez establecida la conexión, podrá usar todas las funciones de audio con el teléfono habilitado para Lync, así como ver la lista completa de los participantes de la conferencia e interactuar con ellos.

