```mermaid
%%{
  init: {
    'theme': 'base',
    'themeVariables': {
        'lineColor': 'darkblue',
        'primaryColor': '#DFEEBD',
        'primaryTextColor': 'black',
        'primaryBorderColor': '#006600',
        'tertiaryColor': 'white',
        'edgeLabelBackground': 'white'
    }
  }
}%%

flowchart
    subgraph CICLOI ["PHASE 0"]
    %% Componentes CICLO I
        CICLOI_title["<span style='font-size: xxx-large;'><b>PHASE 0</b>
        Preparation</span>"]
        AVISO[["
            <span style='font-size: x-large;'>fa:fa-poo
            <b>AVISO INICIAL 
            SINIESTRO</b>
            </span>"]]
        PREPARACION(["
            <span style='font-size: x-large;'>fa:fa-bottle-water
            <b>PREPARACIÓN</b></span>
            Ubicar Póliza y Coberturas
            Extraer Info General
            Exclusiones
            Sublímites / Deducibles
            Copagos / Aseguros"])
    %% Relaciones CICLO I
        AVISO --> PREPARACION
        PREPARACION --> ANALISIS_Inicial
    end

    subgraph CICLOII [" "]
        CICLOII_title["<span style='font-size: xxx-large;'><b> CICLO II </b>
        Preparación del Ajuste</span>"]
        %% Componentes
        COORDINAR_Visita_Ajustador[["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>COORDINAR VISITA
            AJUSTADOR</b></span>
            Coordinar personal
            Ajustador, Cliente y Quantum
            Abrir un Chat
            "]]
        VISITA_Ajustador(["
            <span style='font-size: x-large;'>fa:fa-people-group
            <b>VISITA AJUSTADOR</b></span>
            con personal de Quantum
            "])
        ENVIAR_Requerimientos_Cliente[["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>ENVIAR REQUERIMIENTOS
            AL CLIENTE</b></span>
            <b>Lista de Documentos e Informaciones:</b>
            Cotizaciones, Facturas, Informes de Peritos, Videos, Testigos
            <b>Modelos y Orientación:</b>
            Informes Técnicos, Cartas y Formularios de Reclamos
            "]]
        SEGUIMIENTO_Requerimientos_Cliente(["
            <span style='font-size: x-large;'>fa:fa-list-check
            <b>SEGUIMIENTO REQUERIMIENTOS
            AL CLIENTE</b></span>
            Recibir y verificar
            Documentos e Informaciones
            "])
        RECOLECTAR_Info(["
            <span style='font-size: x-large;'>fa:fa-folder-open
            <b>RECOLECTAR
            DOCS & INFO</b></span>
            "])
        ANALIZAR_Info(["
            <span style='font-size: x-large;'>fa:fa-eye
            <b>ANÁLISIS DE DOCUMENTOS
            & INFORMACION</b></span>
            Orientación Mejorar
            soporte Documental
            "])
        ESTA_Completa{"
            <span style='font-size: x-large;'>fa:fa-square-check
            <b>¿ESTÁ COMPLETA?</b></span>
            Si hace falta info o documentación.
            "}
        ENVIAR_Nuevos_Requerimientos_Cliente(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>ENVIAR NUEVOS
            REQUERIMIENTOS AL CLIENTE</b></span>
            Según sean requeridos por el caso
            "])
        PROYECCION_Inicial(["
            <span style='font-size: x-large;'>fa:fa-calculator
            <b>PROYECCIÓN AJUSTE INICIAL</b></span>
            Ajuste Interno
            "])
        ENVIAR_Ajustadores[["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>ENVIAR A
            AJUSTADORES</b></span>
            Docs & Info
            "]]
        SEGUIMIENTO_Ajustadores(["
            <span style='font-size: x-large;'>fa:fa-list-check
            <b>SEGUIMIENTO A
            AJUSTADORES</b></span>
            Leer borrador de Ajuste
            Identificar si hay nuevos
            requerimientos
            "])
        SURGEN_NuevosRequerimientos{"
            <span style='font-size: x-large;'>fa:fa-question
            <b>¿SURGEN NUEVOS REQUERIMIENTOS?</b></span>
            Requeridos por los ajustadores o su informe
            "}
        ARCHIVAR_Expediente(["
            <span style='font-size: x-large;'>fa:fa-keyboard
            <b>ARCHIVAR
            EXPEDIENTE DIGITAL</b></span>
            "])
        %% Relaciones CICLO II
        COORDINAR_Visita_Ajustador --> VISITA_Ajustador
        --> SURGEN_NuevosRequerimientos
        ENVIAR_Requerimientos_Cliente --> SEGUIMIENTO_Requerimientos_Cliente
        --> RECOLECTAR_Info --> ANALIZAR_Info
        --> ESTA_Completa
        --> |No está
        completa| ENVIAR_Nuevos_Requerimientos_Cliente 
        --> SEGUIMIENTO_Requerimientos_Cliente
        ESTA_Completa
        --> |Sí está
        completa| PROYECCION_Inicial
        ESTA_Completa
        ----> ENVIAR_Ajustadores
        ENVIAR_Ajustadores --> SEGUIMIENTO_Ajustadores
        --> SURGEN_NuevosRequerimientos
        --> |Sí hay
        nuevos
        requerimientos| ENVIAR_Nuevos_Requerimientos_Cliente 
        SURGEN_NuevosRequerimientos
        --> |No hay
        nuevos
        requerimientos| ARCHIVAR_Expediente
    end

    subgraph CICLOIII [" "]
        CICLOIII_title["<span style='font-size: xxx-large;'><b> CICLO III </b>
        Negociación de Ajuste</span>"]
        %% Componentes
        RECIBIR_Ajuste[["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>RECIBIR AJUSTE</b></span>
            Actualizar Status
            "]]
        ANALISIS_Ajuste(["
            <span style='font-size: x-large;'>fa:fa-pen-ruler
            <b>ANÁLISIS AJUSTE</b></span>
            Ajustar Proyecciones
            "])
        COMPARTIR_Ajuste(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>COMPARTIR AJUSTE &
            ANÁLISIS DE AJUSTE</b></span>
            Con el Cliente
            Con el Asociado
            "])
        DECIDIR_Ajuste{"
            <span style='font-size: x-large;'>fa:fa-circle-question
            <b>DECIDIR SOBRE AJUSTE</b></span>
            Decidir si hace falta apelar
            o completar información y documentos
            "}
        DECIDIR_Ajuste_Razones{"
            <span style='font-size: x-large;'>fa:fa-circle-question
            <b>RAZONES PARA
            NO ACEPTAR</b></span>
            Acciones a tomar
            en cada caso
            "}
        NEGOCIAR_Salvamentos(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>NEGOCIAR VALOR
            SALVAMENTOS</b></span>
            En caso existan
            "])
        PREPARAR_Apelacion(["
            <span style='font-size: x-large;'>fa:fa-keyboard
            <b>PREPARAR APELACIÓN</b></span>
            Desarrollar y documentar
            justificaciones y expectativas
            "])
        PREPARAR_Info_Adicional(["
            <span style='font-size: x-large;'>fa:fa-keyboard
            <b>PREPARAR
            INFORMACIÓN ADICIONAL</b></span>
            Completar información
            y documentos
            "])
        ENVIAR_Revision(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>ENVIAR SOLICITUD
            DE REVISIÓN</b></span>
            Remitir a los ajustadores,
            asegurado y asociado
            "])
        SEGUIMIENTO_Apelacion(["
            <span style='font-size: x-large;'>fa:fa-list-check
            <b>SEGUIMIENTO A
            REVISIÓN</b></span>
            Identificar si hay nuevos
            requerimientos
            "])
        RECIBIR_Respuesta_Apelacion(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>RECIBIR RESPUESTA</b></span>
            Actualizar Status
            "])
        SOLICITAR_Ajuste_Final(["
            <span style='font-size: x-large;'>fa:fa-keyboard
            <b>SOLICITAR AJUSTE FINAL</b></span>
            Al Ajustador
            "])
        SEGUIMIENTO_Ajuste_Final(["
            <span style='font-size: x-large;'>fa:fa-list-check
            <b>SEGUIMIENTO
            AJUSTE FINAL</b></span>
            Hasta recibirlo
            "])
        RECIBIR_Ajuste_Final(["
            <span style='font-size: x-large;'>fa:fa-list-check
            <b>RECIBIR
            AJUSTE FINAL</b></span>
            De los Ajustadores
            "])
        REVISAR_Ajuste_Final(["
            <span style='font-size: x-large;'>fa:fa-pen-ruler
            <b>REVISAR
            AJUSTE FINAL</b></span>
            Verificar todo
            "])
        DECIDIR_Ajuste_Final{"
            <span style='font-size: x-large;'>fa:fa-circle-question
            <b>DECIDIR SOBRE
            AJUSTE FINAL</b></span>
            Decidir si hace falta apelar
            o completar información y documentos
            "}
        FIRMAR_Ajuste_Final(["
            <span style='font-size: x-large;'>fa:fa-pen-ruler
            <b>FIRMAR Y SELLAR
            AJUSTE FINAL</b></span>
            El Cliente 
            lo firma y sella y
            lo envía a Quantum
            "])

        ENVIAR_Ajuste_Final[["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>ENVIAR
            AJUSTE FINAL</b></span>
            A la Aseguradora
            con copia al
            Cliente y al Asociado
            "]]
    %% Relaciones CICLO III
        RECIBIR_Ajuste --> ANALISIS_Ajuste
        --> COMPARTIR_Ajuste
        --> DECIDIR_Ajuste
        DECIDIR_Ajuste --> | No se
        Acepta | DECIDIR_Ajuste_Razones
        DECIDIR_Ajuste_Razones --> | Desacuerdo en
        Salvamentos | NEGOCIAR_Salvamentos
        DECIDIR_Ajuste_Razones --> | Hace Falta
        Información | PREPARAR_Info_Adicional
        DECIDIR_Ajuste_Razones --> | Desacuerdo en
        Condiciones | PREPARAR_Apelacion
        NEGOCIAR_Salvamentos
        --> ENVIAR_Revision
        PREPARAR_Info_Adicional
        --> ENVIAR_Revision
        PREPARAR_Apelacion
        --> ENVIAR_Revision
        ENVIAR_Revision
        --> SEGUIMIENTO_Apelacion
        --> RECIBIR_Respuesta_Apelacion
        --> DECIDIR_Ajuste
        DECIDIR_Ajuste --> | Se Acepta
        el Ajuste | SOLICITAR_Ajuste_Final
        --> SEGUIMIENTO_Ajuste_Final
        --> RECIBIR_Ajuste_Final
        --> REVISAR_Ajuste_Final
        --> DECIDIR_Ajuste_Final
        DECIDIR_Ajuste_Final
        --> | No se
        Acepta | DECIDIR_Ajuste_Razones
        DECIDIR_Ajuste_Final
        --> | Sí se
        Acepta | FIRMAR_Ajuste_Final
        ---> ENVIAR_Ajuste_Final
    end

    subgraph CICLOIV [" "]
        CICLOIV_title["<span style='font-size: xxx-large;'><b>CICLO IV</b>
        Pago del Reclamo</span>"]
        %% Componentes
        DEFINIR_Pago[["
            <span style='font-size: x-large;'>fa:fa-comments-dollar
            <b>DEFINIR
            FORMA DE PAGO</b></span>
            Por Transferencia, Cheque
            A Nombre de Quién
            "]]
        SEGUIMIENTO_Cliente(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>SEGUIMIENTO
            AL CLIENTE</b></span>
            Sobre la forma y condiciones de pago
            "])
        OBTENER_Acuerdo(["
            <span style='font-size: x-large;'>fa:fa-file
            <b>OBTENER
            ACUERDO FINALIZADO</b></span>
            Firmado por el Cliente
            (Actualmente lo
            firma Quantum)
            "])

        FIRMA_Acuerdo{"
            <span style='font-size: x-large;'>fa:fa-comments
            <b>QUIEN FIRMA
            EL ACUERDO</b></span>
            ¿el cliente
            o Quantum?
            "}

        OBTENER_Consentimiento(["
            <span style='font-size: x-large;'>fa:fa-file
            <b>OBTENER
            AUTORIZACIÓN PARA FIRMA</b></span>
            En caso que firma Quantum, obtener autorización por escrito del cliente
            "])

        ARCHIVAR_Consentimiento(["
            <span style='font-size: x-large;'>fa:fa-folder-open
            <b>ARCHIVAR AUTORIZACIÓN
            DE FIRMA</b></span>
            En el Expediente Digital del caso
            "])

        ENVIAR_Acuerdo(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>ENVIAR 
            ACUERDO FINALIZADO</b></span>
            A la Aseguradora o Al Ajustador
            "])
        ARCHIVAR_Acuerdo(["
            <span style='font-size: x-large;'>fa:fa-folder-open
            <b>ARCHIVAR
            ACUERDO FINALIZADO</b></span>
            En Expediente Digital
            "])
        OBTENER_Fecha_Pago(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>OBTENER FECHA PAGO</b></span>
            Actualizar Status
            "])
        SEGUIMIENTO_Pago(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>SEGUIMIENTO AL
            PAGO</b></span>
            Hasta su
            realización
            "])
        DIFICULTAD_Pago{"
            <span style='font-size: x-large;'>fa:fa-comments
            <b>DEMORA O DIFICULTAD
            EN PAGO
            </b></span>
            Es necesario
            escalar
            "}
        ESCALAR_Gestion(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>ESCALAR GESTION</b></span>
            Al Asociado,
            Al Gerente
            "])
        REALIZACION_pago(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>REALIZACIÓN 
            DE PAGO</b></span>
            Por la 
            Aseguradora
            "])
        GESTIONAR_Recibo(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>GESTIONAR RECIBO Y
            DESCARGOS</b></span>
            Con el Cliente
            "])
        ENCUESTA_Satisfaccion(["
            <span style='font-size: x-large;'>fa:fa-thumbs-up
            <b>ENCUESTA
            DE SATISFACCIÓN</b></span>
            Enviada lo más pronto
            posible al cliente
            "])

        REGISTRAR_Cierre[["
            <span style='font-size: x-large;'>fa:fa-keyboard
            <b>REGISTRAR CIERRE</b></span>
            Actualizar Status, Plataformas
            y Expedientes
            "]]

        REGISTRAR_Cierre_Expediente(["
            <span style='font-size: x-large;'>fa:fa-keyboard
            <b>ACTUALIZAR
            EXPEDIENTE</b></span>
            Archivar Recibo
            y Descargos
            "])

        REGISTRAR_Cierre_Korrenet(["
            <span style='font-size: x-large;'>fa:fa-keyboard
            <b>ACTUALIZAR
            KORRENET</b></span>
            Actualizar Status
            y Bitácora
            "])

        REGISTRAR_Cierre_Planner(["
            <span style='font-size: x-large;'>fa:fa-keyboard
            <b>ACTUALIZAR
            PLANNER</b></span>
            Revisar, Comentar
            y Cerrar Tareas
            "])

        SEGUIMIENTO_PostCierre(["
            <span style='font-size: x-large;'>fa:fa-comments
            <b>SEGUIMIENTO
            POST CIERRE</b></span>
            Contactar al cliente entre
            15 y 90 días más tarde
            "])

    %% Relaciones CICLO IV

         DEFINIR_Pago
         --> SEGUIMIENTO_Cliente
         --> OBTENER_Acuerdo

        OBTENER_Acuerdo
         --> FIRMA_Acuerdo

        FIRMA_Acuerdo
         --> | Firma Quantum | OBTENER_Consentimiento
         --> ARCHIVAR_Consentimiento
         --> ENVIAR_Acuerdo

        FIRMA_Acuerdo
         --> | Firma Cliente | ENVIAR_Acuerdo
         --> ARCHIVAR_Acuerdo
         --> OBTENER_Fecha_Pago
         --> SEGUIMIENTO_Pago
         DIFICULTAD_Pago
         --> | No hay demora
          o dificultad | REALIZACION_pago
         --> GESTIONAR_Recibo
         --> ENCUESTA_Satisfaccion
         --> REGISTRAR_Cierre
         
        REGISTRAR_Cierre
         --> REGISTRAR_Cierre_Expediente
        REGISTRAR_Cierre
         --> REGISTRAR_Cierre_Korrenet
        REGISTRAR_Cierre
         --> REGISTRAR_Cierre_Planner

        REGISTRAR_Cierre
         ----> SEGUIMIENTO_PostCierre

        SEGUIMIENTO_Pago
         --> DIFICULTAD_Pago
         --> | Sí hay demora
          o dificultad | ESCALAR_Gestion
         --> SEGUIMIENTO_Pago
    end

%% RELACIONES CICLOS
    CICLOI ==> CICLOII ==> CICLOIII ==> CICLOIV

%% ESTILOS
    %% Nodos
        classDef default fill:#EDEDF7,stroke:darkblue,stroke-width:5px;
        classDef CICLOS stroke:#006600,stroke-width:10px;
        classDef CICLO_titles color:#003300,fill:#84bd00,stroke:none;
        classDef Inicios fill:#84bd0044,stroke:darkgreen,stroke-width:5px;
        classDef Finales fill:#F7EDED,stroke:darkred,stroke-width:5px;
        classDef Opcionales fill:#FFEDCC,stroke:darkorange,stroke-width:5px,stroke-dasharray:5 5;
        class CICLOI_title,CICLOII_title,CICLOIII_title,CICLOIV_title CICLO_titles
        class CICLOI,CICLOII,CICLOIII,CICLOIV CICLOS
        class AVISO,ENVIAR_Requerimientos_Cliente,COORDINAR_Visita_Ajustador Inicios
        class RECIBIR_Ajuste,DEFINIR_Pago Inicios
        class REGISTRO_Plataformas,ENVIAR_Ajustadores,ENVIAR_Ajuste_Final,REGISTRAR_Cierre Finales
        class SEGUIMIENTO_Ajustadores,SEGUIMIENTO_PostCierre Opcionales
    %% Líneas
        linkStyle default stroke-width:3px,stroke:darkblue;
```
