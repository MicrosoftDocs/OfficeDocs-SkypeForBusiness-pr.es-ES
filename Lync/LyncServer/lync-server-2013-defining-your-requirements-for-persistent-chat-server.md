---
title: "Lync Server 2013: Definición de los requisitos para el servidor de chat persistente "
TOCTitle: Definición de los requisitos de la organización para el servidor de chat persistente
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48275313
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definición de los requisitos de la organización para el servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2014-01-15_

Antes de implementar Servidor de chat persistente en su organización, es fundamental considerar las siguientes preguntas claves para optimizar su implementación:

  - ¿Quién (perfil de usuario) debe estar habilitado para Servidor de chat persistente? Servidor de chat persistente se habilita mediante una directiva que puede establecerse a nivel global, de sitio, de grupo o de usuario.

  - ¿Cuántos usuarios (escala) deben estar habilitados para Servidor de chat persistente? Servidor de chat persistente admite 150.000 usuarios aprovisionados (habilitados por directiva) y un máximo de 80.000 usuarios concurrentes utilizando Servidor de chat persistente. Un solo Servidor de chat persistente puede admitir 20.000 conectados y un solo Grupo de servidores de chat persistente puede tener hasta 4 servidores activos para un total de 80.000 usuarios conectados de forma concurrente.

  - ¿Está migrando desde una versión anterior de Servidor de chat en grupo o está implementando Servidor de chat persistente por primera vez?

  - ¿Hay requisitos de cumplimiento? Servidor de chat persistente admite el cumplimiento. El servicio de cumplimiento se ejecuta combinado con la base de datos de cumplimiento de Servidor de chat persistenteServidor front-end, frente al requisito de un equipo independiente en anteriores implementaciones de Servidor de chat en grupo. El cumplimiento es opcional y si se elige, requiere una base de datos de cumplimiento que debe configurarse para almacenar eventos y datos de cumplimiento. Puede también configurar un adaptador para obtener datos de la base de datos de cumplimiento y convertirlos a otro formato (como archivos XML o archivos alojados de Exchange).

  - ¿Cómo desea controlar los ámbitos, los límites éticos y el acceso? Puede definir **Categorías** para segregar estos límites y elegir quién puede estar en salones que se crean en cada una de estas categorías.

  - ¿Qué desea para controlar quién puede crear salones? Puede configurar **Creadores**, correspondientes a las categorías, que pueden crear salones. Los creadores pueden asignar otros miembros como **Administradores de salones de chat** para la administración continua de los salones (agregar o quitar miembros adicionales), según el ámbito de **AllowedMembers/DeniedMembers** configurado por la categoría.

  - ¿Cómo desea crear salones? Servidor de chat persistente proporciona una función basada en web para la administración y creación de salones. Esto puede iniciarse desde el cliente de Lync 2013. Puede elegir la definición de una solución personalizada (con el Kit de desarrollo de software (SDK) de Servidor de chat persistente) implementa sus requisitos y flujos de trabajo empresariales y configura Servidor de chat persistente para dirigir a los usuarios a su solución personalizada.

  - ¿Qué tipo de complemento desea suministrar? El **complemento** mejora la experiencia en el salón aprovechando el panel de extensibilidad del cliente de Lync 2013 para proporcionar un contexto relevante al salón. Puede elegir qué complementos generales podrían ser más útiles (por ejemplo, el sitio web de la empresa, los documentos de colaboración interna, etc.). Los administradores del salón de chat pueden elegir uno de los complementos registrados y asociarlo a sus salones, si lo desean.

  - ¿Qué tipo de requisitos de alta disponibilidad y recuperación ante desastres tiene? Servidor de chat persistente admite el reflejo de SQL Server y la agrupación de clústeres de SQL Server para alta disponibilidad y admite hasta 8 servidores (4 activos y 4 en espera) en un grupo extendido con envío de registro de SQL Server para la recuperación ante desastres.

  - ¿Existen requerimientos legales? Si su empresa está en un país o una región donde los datos deben mantenerse de forma global, puede que necesite implementar varios Grupos de servidores de chat persistente, cada local a una geografía específica. Un salón, categoría o complemento no se distribuye en grupos, pertenece solo a un Grupo de servidores de chat persistente. Puede administrar el conjunto de categorías, complementos y salones para cada Grupo de servidores de chat persistente. Los usuarios pueden configurarse para tener acceso a salones en uno o más grupos, mediante el ámbito de AllowedMembers o el ámbito de pertenencia del salón, dependiendo de cómo diseñe sus categorías.
    
    > [!IMPORTANT]  
    > Tener varios Grupos de servidores de chat persistente no le da más escala (todavía solo puede tener 80.000 usuarios conectados simultáneamente en todos los Grupos de servidores de chat persistente). El principal motivo para soportar varios Grupos de servidores de chat persistente es asistir inquietudes legales.
    

