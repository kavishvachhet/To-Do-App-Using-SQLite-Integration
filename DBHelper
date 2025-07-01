import 'dart:io';
import 'package:path/path.dart';
import 'package:path_provider/path_provider.dart';
import 'package:sqflite/sqflite.dart';

class DBHelper {
  // Singleton
  DBHelper._();
  static final DBHelper _instance = DBHelper._();
  static DBHelper getInstance() => _instance;

  static const String TABLE_NOTE = "note";
  static const String COLUMN_NOTE_SNO = "sr_no";
  static const String COLUMN_NOTE_TITLE = "title";
  static const String COLUMN_NOTE_DESC = "desc";

  Database? _myDb;

  // Get or open the DB
  Future<Database> getDB() async {
    _myDb ??= await openDB();
    return _myDb!;
  }

  Future<Database> openDB() async {
    Directory appDir = await getApplicationDocumentsDirectory();
    String dbPath = join(appDir.path, "Notes.db");

    return await openDatabase(
      dbPath,
      onCreate: (db, version) {
        db.execute(
            "CREATE TABLE $TABLE_NOTE ("
                "$COLUMN_NOTE_SNO INTEGER PRIMARY KEY AUTOINCREMENT, "
                "$COLUMN_NOTE_TITLE TEXT, "
                "$COLUMN_NOTE_DESC TEXT)"
        );
      },
      version: 1,
    );
  }

  // Add note
  Future<bool> addNote({required String mtitle, required String mdesc}) async {
    var db = await getDB();

    int rowsAffected = await db.insert(TABLE_NOTE, {
      COLUMN_NOTE_TITLE: mtitle,
      COLUMN_NOTE_DESC: mdesc,
    });

    return rowsAffected > 0;
  }

  // Retrieve all notes
  Future<List<Map<String, dynamic>>> getAllNotes() async {
    var db = await getDB();
    List<Map<String, dynamic>> data = await db.query(TABLE_NOTE);
    return data;
  }


  //update data
  Future<bool> updatenote({required String title,required String des,required int id}) async {
      var db = await getDB();

      int row = await db.update(TABLE_NOTE, {
        COLUMN_NOTE_TITLE: title,
        COLUMN_NOTE_DESC: des,
      }, where: "$COLUMN_NOTE_SNO = $id");

      return row > 0;

  }

  Future<bool> deletenote({required int id}) async {
    var db = await getDB();

   int row = await db.delete(TABLE_NOTE,where: "$COLUMN_NOTE_SNO = ?", whereArgs: ['$id']);

    return row > 0;

  }
}
