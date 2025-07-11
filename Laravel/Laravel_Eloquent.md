# Select data
    $variable = Model::get();                                                   // Selects all data
    $variable = Model::where('column_name', 'condition', 'value')->get();       // Selects published data
    $variable = Model::where('column_name', 'condition', 'value')->first();     // Selects first data
    $variable = Model::first();                                                 // Selects first data without filter
    $variable = Model::find(2);                                                 // Selects by id
    $variable = Model::orderBy('column_name', 'order')->get();                  // Selects by asc or desc
    $variable = Model::orderBy('column_name', 'order')->limit('value')->get();  // Selects by asc or desc with limit
    $variable = Model::orderBy('column_name', 'desc')->value('price');          // Selects single value from the first
    
# Insert data
    $variable = new Model();                                                // Create instance first
    $variable -> column_name = 'value';                                   // Insert by column

    $array = ['column_name' => 'value'];                                    // Fillables as array
    $variable = Model::create(array);                                      // Approach 1

    $variable = new Model();                                                /** 
    $variable -> fill($array);                                              * Approach 2
    $variable -> save();                                                    */

    $variable =  new Model($array);                                            /**  Approach 3
    $variable -> save();                                                    */

# Update data
    $variable = Model::find(1);                                             /**
    $variable -> column_name = 'value';                                     * Update by id
    $variable -> save();                                                    */

    Model::updateOrCreate(                                                  /** update else create one by one
        ['column_name' => 'value'],                                         * Where exist
        ['column_name' => 'value']                                          * Update this
        );   

    Model::where('column_name', 'value')                                    /**
        ->where('column_name', 'value')                                     * Mass update using where
        ->update(['column_name' => 'value']);                               */

# Delete data
    $variable = Model::find(1);                                             // Selects data
    $variable -> delete();                                                  // delete data
    $variable -> destroy(['id']);                                           // Mass delete with select by id

    Model::truncate();                                                      // Hard Delete when using softdelete

# Attach and Sync

    $variable->method()->attach([id], [second arg]);                        // Attach id
    $variable->method()->sync([3])                                          // removes current and attach 3
    $variable->method()->syncWithPivotValues([3], [second arg]);            //removes and attach bit with second argument
    $variable->method()->detach([1, 2]);                                    //removes 1 and 2


# Query Data
    $variable = DB::table('table_name')->get();                 // without model
    $variable = Model::query();                                 // with model


# ENV
DB_CONNECTION=[DB]
DATABASE_URL=driver://username::password@host:port/database