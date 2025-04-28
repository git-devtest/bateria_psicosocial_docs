erDiagram
	estres_preguntas ||--|| estres_respuestas : references
	estres_respuestas ||--|| estres_opciones_respuesta : references
	form_datos_generales ||--|| estado_civil : references
	form_datos_generales ||--|| estrato_serv_publicos_vivienda : references
	estres_respuestas ||--|| form_datos_generales : references
	extralaboral_respuestas ||--|| extralaboral_preguntas : references
	extralaboral_opciones_respuesta ||--|| extralaboral_respuestas : references
	extralaboral_respuestas ||--|| form_datos_generales : references
	sexo ||--|| form_datos_generales : references
	form_datos_generales ||--|| ultimo_nivel_estudios : references
	form_datos_generales ||--|| tipo_vivienda : references
	form_datos_generales ||--|| tipo_cargo : references
	form_datos_generales ||--|| tipo_contrato : references
	form_datos_generales ||--|| tipo_salario : references
	intralaboral_a_preguntas ||--|| intralaboral_a_respuestas : references
	intralaboral_a_opciones_respuesta ||--|| intralaboral_a_respuestas : references
	intralaboral_a_respuestas ||--|| form_datos_generales : references
	intralaboral_b_preguntas ||--|| intralaboral_b_respuestas : references
	intralaboral_b_opciones_respuesta ||--|| intralaboral_b_respuestas : references
	intralaboral_b_respuestas ||--|| form_datos_generales : references
	empresas ||--|| usuarios : references
	usuarios ||--|| roles : references

	empresas {
		INTEGER id
		VARCHAR(255) nombre
		VARCHAR(50) nit
		VARCHAR(255) email
		VARCHAR(50) telefono
		TEXT(65535) direccion
		TIMESTAMP fecha_registro
	}

	estado_civil {
		INTEGER id
		VARCHAR(20) estado
	}

	estrato_serv_publicos_vivienda {
		INTEGER id
		VARCHAR(6) estrato
	}

	estres_opciones_respuesta {
		INTEGER id
		VARCHAR(30) etiqueta
		INTEGER valor
	}

	estres_preguntas {
		INTEGER id
		TEXT(65535) descripcion
	}

	estres_respuestas {
		INTEGER id
		INTEGER id_formulario
		INTEGER id_pregunta
		INTEGER id_opcion_respuesta
	}

	form_datos_generales {
		INTEGER id
		DATE fecha_aplicacion
		VARCHAR(12) identificacion_respondiente
		VARCHAR(60) nombre_completo
		INTEGER sexo
		VARCHAR(4) año_nacimiento
		INTEGER estado_civil
		INTEGER ultimo_nivel_estudios
		VARCHAR(60) ocupacion_profesion
		VARCHAR(60) lugar_residencia_actual_ciudad_mpio
		VARCHAR(60) lugar_residencia_actual_depto
		INTEGER estrato_serv_publicos_vivienda
		INTEGER tipo_vivienda
		INTEGER num_personas_dependientes_respondiente
		VARCHAR(60) lugar_trabajo_actual_ciudad_mpio
		VARCHAR(60) lugar_trabajo_actual_depto
		INTEGER cuantos_anios_trabaja_empresa_menos_un_año
		VARCHAR(255) cuantos_anios_trabaja_empresa_mas_un_año
		VARCHAR(60) nombre_cargo_empresa
		INTEGER tipo_cargo
		INTEGER cuantos_anios_desempenia_cargo_empresa_menos_un_año
		INTEGER cuantos_anios_desempenia_cargo_empresa_mas_un_año
		VARCHAR(60) nombre_depto_area_seccion_empresa
		INTEGER tipo_contrato
		INTEGER horas_diarias_trabajo_cargo
		INTEGER tipo_salario
	}

	intralaboral_a_opciones_respuesta {
		INTEGER id
		VARCHAR(30) etiqueta
		INTEGER valor
	}

	intralaboral_a_preguntas {
		INTEGER id
		VARCHAR(255) descripcion
	}

	intralaboral_a_respuestas {
		INTEGER id
		INTEGER id_formulario
		INTEGER id_pregunta
		INTEGER id_opcion_respuesta
	}

	intralaboral_b_opciones_respuesta {
		INTEGER id
		VARCHAR(30) etiqueta
		INTEGER valor
	}

	intralaboral_b_preguntas {
		INTEGER id
		VARCHAR(255) descripcion
	}

	intralaboral_b_respuestas {
		INTEGER id
		INTEGER id_formulario
		INTEGER id_pregunta
		INTEGER id_opcion_respuesta
	}

	logs {
		INTEGER id
		INTEGER usuario_id
		VARCHAR(255) tabla_afectada
		ENUM accion
		TEXT(65535) sentencia_sql
		TIMESTAMP timestamp
	}

	roles {
		INTEGER id
		VARCHAR(50) nombre
	}

	sexo {
		INTEGER id
		VARCHAR(10) genero
	}

	tipo_cargo {
		INTEGER id
		VARCHAR(100) cargo
	}

	tipo_contrato {
		INTEGER id
		VARCHAR(40) contrato
	}

	tipo_salario {
		INTEGER id
		VARCHAR(60) salario
	}

	tipo_vivienda {
		INTEGER id
		VARCHAR(10) tipo
	}

	ultimo_nivel_estudios {
		INTEGER id
		VARCHAR(35) estudio
	}

	usuarios {
		INTEGER id
		VARCHAR(255) nombre
		VARCHAR(255) email
		VARCHAR(255) contrasena
		INTEGER rol_id
		INTEGER empresa_id
	}

	extralaboral_opciones_respuesta {
		INTEGER id
		VARCHAR(30) etiqueta
		INTEGER valor
	}

	extralaboral_preguntas {
		INTEGER id
		VARCHAR(255) descripcion
	}

	extralaboral_respuestas {
		INTEGER id
		INTEGER id_formulario
		INTEGER id_pregunta
		INTEGER id_opcion_respuesta
	}