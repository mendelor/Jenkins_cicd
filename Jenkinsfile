class Spec {

   def classes = []

   def model(args)
   {
      def clazz = new Clazz().named(args.clazz)

      if (args.withAttributes)
      {
         clazz.attributes(args.withAttributes)
      }

      this.classes << clazz

      return this
   }

   def generate()
   {
      def code = ""
      classes.each { clazz ->
         code += "class ${clazz.name} {\n"
         clazz.attributes.each { attr ->
            code += "   def ${attr}\n"
         }
         code += "}"
         code += "\n"
      }
      return code
   }
}
class Clazz {
   def name
   def attributes = []
   def named(name)
   {
      this.name = name
      return this
   }
   def attributes(attributes)
   {
      this.attributes = attributes
   }
}

def spec = new Spec()

def named = { name ->
  return name
}

spec.model( clazz: named("Person"), withAttributes:["name", "age"] )
    .model( clazz: named("Role") )
    .generate()




