


qt-vs-addin-1.2.3-opensource.exe

qt-opensource-windows-x86-msvc2013_64-5.4.2.exe

qt-vs-tools-msvc2013-2.1.1.vsix

QTDIR  设置 C:\Qt\Qt5.4.2\5.4\msvc2013_64 


https://download.qt.io/archive/qt/5.4/5.4.2/

https://download.qt.io/official_releases/vsaddin/


Kinect is    KINECTSDK10_DIR is set as 

C:\Program Files\Microsoft SDKs\Kinect\v1.8\


		volume_resolution[0] = 256;
		volume_resolution[1] = 256;
		volume_resolution[2] = 256;
		voxels_per_meter = 256;

		/** *****************************************************
		* marching cube related
		* ******************************************************/
		marching_cube_level = 0;
		marching_cube_tile_size = 256;
		marching_cube_max_activeVoxel_ratio = 0.2;
		marching_cube_isoValue = 0.f;
		marchingCube_min_valied_weight = 1.f;

		/** *****************************************************
		* warp field related
		* ******************************************************/
		// cannot be larger than warpField::knnK
		warp_knn_k_eachlevel[0] = 4;	// graph-pixel association
		warp_knn_k_eachlevel[1] = 4; // finest graph
		warp_knn_k_eachlevel[2] = KnnK;
		warp_knn_k_eachlevel[3] = KnnK;
		set_warp_radius_search_epsilon(0.025);
		warp_param_softness = 0.05;
		warp_radius_search_beta = 2;
		warp_param_dw_lvup_scale = 0.01f;
		warp_point_step_before_update_node = 1;

		/** *****************************************************
		* dynamic fusion related
		* ******************************************************/
		fusion_max_weight = 512;   // cgw comment 
		fusion_lambda = 200;
		fusion_psi_data = 0.01;
		fusion_psi_reg = 0.001;
		fusion_rigid_distThre = 0.1f; // meter
		fusion_rigid_ICP_iter[0] = 8; // coarse level
		fusion_rigid_ICP_iter[1] = 4;
		fusion_rigid_ICP_iter[2] = 0; // finest level
		fusion_rigid_angleThreSin = sin(45.f*3.14159254f / 180.f);
		fusion_nonRigid_distThre = 0.03f; // meter
		fusion_nonRigid_angleThreSin = sin(90.f*3.14159254f / 180.f);

		fusion_nonRigidICP_maxIter = 3;
		fusion_GaussNewton_maxIter = 2;
		fusion_GaussNewton_diag_regTerm = 1e-5;
		fusion_GaussNewton_fixedStep = 0.;

		// debuging related
		fusion_dumping_each_frame = false;
		fusion_loading_mode = false;
		fusion_enable_nonRigidSolver = true;
		fusion_enable_rigidSolver = true;
		fusion_post_rigid_factor = true;
		fusion_dumping_max_frame = 8000;
		mirror_input = false; 
		load_frameIndx_plus_num = 1;
		solver_enable_nan_check = false;
		
		
		graph_single_level = true;  // cgw change to true 


		graph_remove_small_components_ratio = 0.1f; //code not ready, use this param>=1.f to disable

		if (graph_single_level)  // cgw change to true  // 
		{
			fusion_lambda = 300;
			fusion_GaussNewton_fixedStep = 0.5f;
			warp_param_softness = 0.2;
			fusion_GaussNewton_diag_regTerm = 1e-6;
		}

		/** *****************************************************
		* visualization related
		* ******************************************************/
		view_no_rigid = false;
		view_show_mesh = true;
		view_show_nodes = false;
		view_show_graph = false;
		view_show_corr = false;
		view_show_graph_level = 0;
		view_errorMap_range = 0.01;
		view_activeNode_id = -1;
		view_click_vert_xy[0] = view_click_vert_xy[1] = -1;
		view_show_color = false;

		view_autoreset = false;
		view_autoreset_seconds = 20;
