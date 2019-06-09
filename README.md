# -
just a test
 ``` c#
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.IO;

namespace 恶心的程序
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void 关于ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            //点击“帮助--关于”项时显示的对话框
            MessageBox.Show("版本为1.0版本");
        }

        private void 帮助ToolStripMenuItem2_Click(object sender, EventArgs e)
        {
            //点击“帮助--帮助”项时的对话框
            MessageBox.Show("本程序尚不完善，无法帮助您,后续版本会尽量满足您的要求");
        }

        private void 打开ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            //点击“系统--打开”项时出现文件对话框
            OpenFileDialog ofd = new OpenFileDialog();
            ofd.InitialDirectory = "C:\\";
            ofd.Filter = "txt files(*.txt)|*.txt|All files(*.*)|*.*";
            ofd.FilterIndex = 2;
            ofd.RestoreDirectory = true;
            if (ofd.ShowDialog() == DialogResult.OK)
            {
                //提示信息
                MessageBox.Show("打开文件：" + ofd.FileName);
            }
        }

        private void 退出ToolStripMenuItem1_Click(object sender, EventArgs e)
        {
            if (MessageBox.Show("你真的要退出吗?", "关闭程序", MessageBoxButtons.OKCancel, MessageBoxIcon.Question, MessageBoxDefaultButton.Button2) == DialogResult.OK)
            {
                //点击对话框中的“确定”时退出程序
                Application.Exit();
            }
        }
        //设置该窗体为主窗体点击“计算”下对应按钮显示对应子窗体
        private void 距离和方位角ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            Form2 f = new Form2();
            f.MdiParent = this;
            f.Show();
        }

        private void 交会计算ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            Form3 r = new Form3();
            r.MdiParent = this;
            r.Show();
        }

        private void 角度转换ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            Form4 t=new Form4();
            t.MdiParent=this;
            t.Show();
        }

        private void 矩阵运算ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            Form5 y = new Form5();
            y.MdiParent = this;
            y.Show();
        }
        //点击“窗体”下对应按钮改变窗体排列
        private void 水平平铺ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            this.LayoutMdi(MdiLayout.TileHorizontal);
        }

        private void 垂直平铺ToolStripMenuItem1_Click(object sender, EventArgs e)
        {
            this.LayoutMdi(MdiLayout.TileVertical);
        }

        private void 层叠平铺ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            this.LayoutMdi(MdiLayout.Cascade);
        }

        private void 数据库ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            Form7 j = new Form7();
            j.MdiParent = this;
            j.Show();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            openFileDialog1.Filter = "BMP file(*.bmp)|*.bmp|JPG file(*.jpg)|*.jpg";
            if (openFileDialog1.ShowDialog() == DialogResult.OK)
            {
                Bitmap image = new Bitmap(openFileDialog1.FileName);
                pictureBox1.Image = image;
            }
        }

        private void button2_Click(object sender, EventArgs e)
        {
            SaveFileDialog save = new SaveFileDialog();
            save.Filter = "JPG file(*.jpg)|*.jpg|All file(*.*)|*.*";
            save.ShowDialog();
            string filename = save.FileName;

            Bitmap image = new Bitmap(pictureBox1.Image);
            image.Save(filename);
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        private void 交会三角形绘制ToolStripMenuItem_Click(object sender, EventArgs e)
        {

        }
    }
}

``` c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Windows.Forms;

namespace 恶心的程序
{
    static class Program
    {
        /// <summary>
        /// 应用程序的主入口点。
        /// </summary>
        [STAThread]
        static void Main()
        {
            Application.EnableVisualStyles();
            Application.SetCompatibleTextRenderingDefault(false);
            Application.Run(new login());
        }
    }
}
