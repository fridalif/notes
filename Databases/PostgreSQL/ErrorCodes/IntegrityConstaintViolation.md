КОД || Название|| Описание

 - 23000 || integrity_constraint_violation || Общее нарушение целостности, когда не подпадает ни под одна из условий ниже
 
 - 23001 || restrict_violation || Нарушение RESTRICT при зависимостях (например, удаление при ON DELETE RESTRICT)
 
 - 23502 || not_null_violation || Нарушение NOT NULL
 
 - 23503 || foreign_key_violation || Нарушение внешнего ключа (например, отсутствие записи в таблицах)
 
 - 23505 || unique_violation || Нарушение условия уникальности
 
 - 23514 ||  check_violation || Нарушение условия CHECK
 
 - 23P01 || exclusion_violation || Нарушение условия EXCLUDE (например, когда пересекаются интервалы)