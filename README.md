# schole01
application ecole
using ClassLibrary;
using System;
using System.Collections.Generic;
using System.Data;
using System.Data.SqlClient;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace SCHOOL10
{
    class agentc : individu
    {
        public string typee;

        public agentc(string refe, string nom, string prenom, string typee, DateTime datens, string tel, string mail)
        {
            this.Refe = refe;
            this.typee = typee;
            this.Nom = nom;
            this.Prenom = prenom;
            this.Datens = datens;
            this.Tel = tel;
            this.Mail = mail;
        }
   

        public void ajouter()
        {
            utile.ouvrir();

            utile.comd.Parameters.Clear();
            utile.comd.CommandType = CommandType.StoredProcedure;
            utile.comd.CommandText = String.Format("ajouter_agent ");

            SqlParameter p1 = new SqlParameter("@refe", SqlDbType.VarChar);
            p1.Direction = ParameterDirection.Input;
            p1.Value = this.Refe;
            SqlParameter p2 = new SqlParameter("@nom", SqlDbType.VarChar);
            p2.Direction = ParameterDirection.Input;
            p2.Value = this.Nom;
            SqlParameter p3 = new SqlParameter("@prenom", SqlDbType.VarChar);
            p3.Direction = ParameterDirection.Input;
            p3.Value = this.Prenom;
            SqlParameter p4 = new SqlParameter("@typeagent", SqlDbType.VarChar);
            p4.Direction = ParameterDirection.Input;
            p4.Value = this.typee;
            SqlParameter p5 = new SqlParameter("@datens", SqlDbType.VarChar);
            p5.Direction = ParameterDirection.Input;
            p5.Value = this.Datens;
            SqlParameter p6 = new SqlParameter("@tel", SqlDbType.VarChar);
            p6.Direction = ParameterDirection.Input;
            p6.Value = this.Tel;
            SqlParameter p7 = new SqlParameter("@mail", SqlDbType.VarChar);
            p7.Direction = ParameterDirection.Input;
            p7.Value = this.Mail;
            utile.comd.Parameters.Add(p1);
            utile.comd.Parameters.Add(p2);
            utile.comd.Parameters.Add(p3);
            utile.comd.Parameters.Add(p4);
            utile.comd.Parameters.Add(p5);
            utile.comd.Parameters.Add(p6);
            utile.comd.Parameters.Add(p7);
            utile.comd.ExecuteNonQuery();


            utile.fermer();
        }
        public void modifier()
        {
            
                utile.ouvrir();

            utile.comd.Parameters.Clear();
            utile.comd.CommandType = CommandType.StoredProcedure;
            utile.comd.CommandText = String.Format("modifier_agent");

            SqlParameter p1 = new SqlParameter("@refe", SqlDbType.VarChar);
            p1.Direction = ParameterDirection.Input;
            p1.Value = this.Refe;
            SqlParameter p2 = new SqlParameter("@nom", SqlDbType.VarChar);
            p2.Direction = ParameterDirection.Input;
            p2.Value = this.Nom;
            SqlParameter p3 = new SqlParameter("@prenom", SqlDbType.VarChar);
            p3.Direction = ParameterDirection.Input;
            p3.Value = this.Prenom;
            SqlParameter p4 = new SqlParameter("@typeagent", SqlDbType.VarChar);
            p4.Direction = ParameterDirection.Input;
            p4.Value = this.typee;
            SqlParameter p5 = new SqlParameter("@datens", SqlDbType.VarChar);
            p5.Direction = ParameterDirection.Input;
            p5.Value = this.Datens;
            SqlParameter p6 = new SqlParameter("@tel", SqlDbType.VarChar);
            p6.Direction = ParameterDirection.Input;
            p6.Value = this.Tel;
            SqlParameter p7 = new SqlParameter("@mail", SqlDbType.VarChar);
            p7.Direction = ParameterDirection.Input;
            p7.Value = this.Mail;
            utile.comd.Parameters.Add(p1);
            utile.comd.Parameters.Add(p2);
            utile.comd.Parameters.Add(p3);
            utile.comd.Parameters.Add(p4);
            utile.comd.Parameters.Add(p5);
            utile.comd.Parameters.Add(p6);
            utile.comd.Parameters.Add(p7);
            utile.comd.ExecuteNonQuery();


            utile.fermer();
        }
        public void supprimer()
        { }
    }
}
