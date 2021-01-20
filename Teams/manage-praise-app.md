---
title: Administrar la aplicación Elogiar en el Centro de administración de Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Obtenga más información sobre la configuración de administración en la aplicación Elogiar en el Centro de administración de Microsoft Teams
ms.openlocfilehash: 122e7f0ffad914e62ede56ebd1811d1504f3fcd7
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909194"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Administrar la aplicación Elogiar en el Centro de administración de Microsoft Teams

> [!NOTE]
> Los administradores deben tener una licencia de Teams para acceder a esta característica. Si intenta acceder a esta característica sin una licencia de Teams, verá un mensaje de error.

La aplicación Elogiar en Microsoft Teams ayuda a los usuarios a mostrar su agradecimiento a los miembros de su organización o clase. Con una selección de conjuntos de distintivos entre los que elegir y la opción de crear sus propios distintivos, Elogiar está diseñado para ayudar a reconocer el esfuerzo realizado en la amplia gama de trabajo que hacen los usuarios de Teams, desde educadores hasta Trabajadores al frente. Para obtener más información, consulte [Enviar elogio a las personas.](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)

Los administradores pueden controlar qué distintivos están disponibles para su organización desde el Centro de administración de Microsoft Teams. En el panel de navegación izquierdo, vaya **a aplicaciones de Teams > Administrar aplicaciones.** En la lista de aplicaciones, haga clic en **Elogiar** y, a continuación, **seleccione Configuración.**  Desde aquí, puede elegir habilitar los conjuntos de distintivo predeterminados e integrados y crear los distintivos personalizados.

![Captura de pantalla de la pestaña Configuración de la aplicación Elogiar](media/manage-praise-app-settings.png)

> [!NOTE]
> La característica de la aplicación Elogiar no está disponible para las nubes de la administración pública de EE. UU.

## <a name="use-built-in-badge-sets"></a>Usar conjuntos de distintivos integrados

Los conjuntos integrados son colecciones de distintivos diseñados por Microsoft para la aplicación Elogiar. Los administradores no pueden modificar estos conjuntos. El conjunto de distintivos predeterminado ya está habilitado y disponible en la aplicación Elogiar. Para cambiar la disponibilidad del conjunto predeterminado o de cualquier conjunto de distintivos, cambie el botón de alternancia correspondiente a Activar o Desactivar. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Distintivos predeterminados

El conjunto de distintivos predeterminado está diseñado para ayudar a los usuarios de Teams a reconocer a sus compañeros para ir más allá con su trabajo.

![Vista previa del conjunto de distintivos predeterminado](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Distintivos de aprendizaje social y emocional para la educación

Los profesores pueden reconocer a alumnos individuales sus logros y comportamientos en el aprendizaje social y emocional (SEL) con distintivos que ilustran estos conceptos.

![Vista previa de los distintivos de aprendizaje social y emocional para la educación](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Crear sus propios distintivos

Seleccione **Crear un distintivo personalizado.** Desde aquí, puede diseñar un distintivo personalizado en el panel lateral. Puede crear hasta 25 distintivos personalizados. 

![Captura de pantalla del panel Crear un distintivo personalizado](media/manage-praise-app-create-custom-badge.png)

1. Escriba un nombre de distintivo. Este es el nombre que aparecerá en el distintivo cuando los usuarios envíen elogios.

2. Establezca los colores del distintivo. Para establecer el texto y los colores de fondo del distintivo, debe escribir los colores como valores hexadecimales (hexadecimales).

   > [!TIP]
   > Si no conoce los valores hexadecimales, este artículo incluye una introducción [rápida](#hex-colors-intro) para mostrarle cómo usarlos.

3. Cargar una imagen de insignia. El tipo de archivo aceptado es . PNG. El archivo de imagen debe ser inferior a 40 KB con unas dimensiones máximas de 216 x 216 píxeles.
![Distintivo con los campos de fondo, texto e imagen etiquetados](media/praise-app-badge-fields.png)

4. Localiza el nombre del distintivo: en **Nombres de distintivo localizados,** selecciona **Agregar.** Seleccione la configuración regional que quiera de la lista desplegable. A continuación, escriba el nombre del distintivo en el idioma designado.

5. Excluir el distintivo de configuraciones regionales específicas: En **Excluir distintivo de estas configuraciones regionales,** seleccione **Agregar.** Seleccione las configuraciones regionales que desee excluir de la lista desplegable.

6. Seleccione **Aplicar.** El nuevo distintivo aparecerá ahora en la tabla de distintivos personalizados.

> [!NOTE]
> Si se omiten los pasos 4 y 5, el distintivo estará en el idioma predeterminado para todas las configuraciones regionales.
>
> Cuando haya terminado de realizar cambios en la selección del distintivo, asegúrese de seleccionar **Enviar.** Pueden tardar unas horas antes de que estos cambios estén disponibles para su organización.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Especificar colores con valores hexadecimales

Los valores de color hexadecimales son cadenas de seis dígitos hexadecimales que representan la intensidad del rojo (RR), el verde (GG) y el azul (BB) en un color específico en una escala de 00 a FF. Al juntar los valores de los tres colores, obtiene un valor hexadecimal: #RRGGBB

Por ejemplo, el valor hexadecimal del color rojo es #FF0000 porque el rojo está establecido en el valor más alto posible, FF, y verde y azul se establecen al valor más bajo posible, 00.

Para explorar diferentes colores y sus valores hexadecimales, consulte el selector [de colores de Bing.](https://www.bing.com/search?q=color+picker)

A continuación se muestra una lista de colores de ejemplo para empezar:

|Color  |Valor hexadecimal|
|-------|---------|
|![Color hexadecimal #FF6666](media/hexColor1.png)|  #FF6666   |
|![Color hexadecimal #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![Color hexadecimal #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![Color hexadecimal #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![Color hexadecimal #800080](media/hexColor5.png)|  #800080   |
|![Color hexadecimal #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Procedimientos recomendados para crear distintivos personalizados

**Envía todos tus distintivos a la vez.** Como los nuevos distintivos tardan un tiempo en procesarse, es mejor agregar todos los distintivos personalizados a la tabla antes de enviarlos.

**A la hora de elegir colores, tenga en cuenta la accesibilidad.** Algunos colores van juntos mejor que otros.  Cree contraste entre el texto y los colores de fondo para facilitar la lectura del nombre del distintivo. Por ejemplo, si ha elegido un color de fondo oscuro, elija un color de texto claro.

**Al seleccionar una imagen, ten en cuenta las dimensiones del distintivo.** Para obtener la mejor calidad, se recomienda cargar un archivo de imagen de 216 x 216 píxeles (que son las dimensiones máximas). Evite estirar o distorsionar la imagen para que se ajuste a estas dimensiones.

**Si la imagen del distintivo no es rectangular, haga la imagen transparente.** Tendrá que hacer esto antes de cargar el archivo de imagen en Elogiar.

![Left: badge with non-transparent image, right: badge with transparent image](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Activos del conjunto de distintivos

Los conjuntos de distintivos integrados no se pueden modificar, por lo que cuando se habilita un conjunto integrado, todos los distintivos del conjunto se agregan a la aplicación Elogiar. Si desea agregar distintivos específicos de un conjunto integrado y dejar fuera a otros usuarios, vuelva a crear los distintivos que desea usar como distintivos personalizados. Puede descargar la imagen del distintivo y buscar el texto y los colores de fondo de los distintivos de conjuntos integrados en las tablas siguientes.

### <a name="default-badges-assets"></a>Activos de distintivos predeterminados

</br>

|Nombre del distintivo     |Archivo de imagen  |Color del texto | Color de fondo |
|---------------|------------|---------- |--------|
|Logre       |[Conseguir PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Increíble        |[PNG increíble](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Entrenador          |[Entrenador PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Insaltez        |[Png png descánso](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Creativo       |[PNG creativo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Ambos inclusive      |[Png incluido](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Kind Heart     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Liderazgo     |[PNG de liderazgo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Que se ha       |[Optimism PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Solucionador de problemas |[Png para resolver problemas](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Jugador de equipo    |[Jugador de equipo PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Gracias      |[Gracias PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Distintivos de aprendizaje social y emocional para los activos de la educación

</br>

|Nombre del distintivo        |Archivo de imagen  |Color del texto | Color de fondo |
|------------------|------------|---------- |--------|
|Comunicación     |[PNG de comunicación](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Pensamiento crítico |[PNG de pensamiento crítico](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Curiosidad         |[Png navideña](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empatía           |[Emática PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Objetivo de la búsqueda      |[Png de la búsqueda de objetivos](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivación        |[Motivación PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistición       |[Png de persistición](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Respetar           |[Respetar PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Responsabilidad    |[PNG de responsabilidad](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Conciencia de uno mismo    |[PNG de conciencia personal](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Administración por su cuenta   |[PNG de administración independiente](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Ideación    |[Thought png](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
